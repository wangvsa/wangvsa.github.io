+++
title = "Posix"
date = "2024-12-15T21:01:59-08:00"

#
# description is optional
#
# description = "An optional description for SEO. If not provided, an automatically created summary will be used."

tags = []
+++


In the last couple of years and now, I have been mostly working on HPC I/O related topics.
One particular question I am trying to answer is: *Can we finally ditch POSIX I/O in HPC?*
POSIX is a standard for specifying the operating systems, which of course, include file systems. 
The POSIX standard is widely used for implementing file systems, ranging from the local file systems (e.g., xfs and ext4) on your laptops to the parallel file systems (e.g., Lustre and GPFS) deployed by the world's largest supercomputers.

However, the issue is, POSIX is not really a good fit for HPC---in fact, it has plagued the HPC environments for years. POSIX was initially designed (decades ago) for use by a single machine with a single storage device. It was designed more towards compatibility rather than performance. Here is an article by Dr. Lockwood on [why POSIX is so bad](https://www.nextplatform.com/2017/09/11/whats-bad-posix-io/). In the context of HPC, the major performance road-blocker is its strict consistency semantics. POSIX imposes a consistency model called sequential consistency, which requires that every *write* operation must become immediately visible to all subsequent *read* operations. This means that if a process on one node writes a few bytes to a file, then such updates must be visible immediately to all other processes on all nodes.

Since I/O operations are much more expensive than CPU operations, basically all file systems (local or parallel) use some sort of caching mechanism to hide the cost of the I/O operations. Maintaining consistency with caching becomes more complicated. Nevertheless, it is relatively easy and cheap to maintain on single machines. But for parallel file systems with distributed caching, it can be extremely expensive which significantly limits scalability. Mostly widely deployed parallel file systems use sophisticated distributed locks to guarantee sequential consistency.

If you are interested in this, here's a position paper I wrote:
Revisiting



This is a page about »POSIX«.
