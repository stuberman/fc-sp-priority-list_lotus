# Multi GPU Scheduling not working correctly on lotus-worker

## Description
The enhanced scheduler has made it possible for a lotus-worker to take on multiple PC2 or C2 jobs, which is a good start, 
but the needed corresponding changes was never implemented on the lotus-worker side.

GPU-lock file to lock the GPU to only one job at ta time.
Still assigns multiple GPUs to one job (which is highly inefficient)

## Related Filecoin Issues
https://github.com/filecoin-project/lotus/discussions/7945#discussioncomment-2065134 

## Desired Implementation
The lotus-worker should

1. Allow multiple jobs to run on the GPU at the same time. Basically the GPU can run another job in parallel for each 8.8GiB available Video memory. 
2. Only use 1 GPU for a job - don't spread it cross multiple GPUs, as this does not speed up sealing efficiently. 
3. If multiple GPUs available for the worker, then lotus-worker should just distribute next job to next available GPU.
4. Lotus-worker should have 1 thread running for each job (when feeding a job on the GPU)

Desired Implementation with practical example: 
GPU Server with 2x RTX 3090, 1024 GiB memory and 64 Cores: 
1. Only 1 lotus-worker process is running
2. Allow both PC2 and C2 jobs
3. C2_32G_GPU_UTILIZATION=0.5 and PC2_32G_GPU_UTILIZATION=0.5 is set for scheduling that each RTX 3090 can run 2 jobs in parallel
4. Run 4 C2 jobs in parallel: Lotus-worker picks up all 4 jobs. Runs 2 jobs on each GPU in full parallel. 
5. Doing GPU intense part, CPU will be running 100% load on 4 threads (one for each job on the two GPUs)
6. Expected behavior should be equal to running 4 individual lotusworkers: 
each with different TMPDIR,
2 CUDA_VISIBLE_DEVICES=0,
2 CUDA_VISIBLE_DEVICES=1 
  
