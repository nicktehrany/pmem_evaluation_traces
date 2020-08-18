# Function Traces - "Evaluating Performance Characteristics of the PMDK Persistent Memory Software Stack"

These are all the different traces mentioned throughout my BSc Thesis. All traces were collected using ftrace (<https://elinux.org/Ftrace>).

## mmap_cost
Function tracing of calling ```mmap``` on the different file systems to identify if page table entries are set up on the function call, and if so how many.
We call ```mmap``` on a 1GiB file on the following file systems: ext4, ext4-DAX, xfs, xfs-DAX, and an anonymous mmap (with MAP_SHARED flag and MAP_PRIVATE flag).
The flags only changed the function calls for anonymous mappings, therefore file system traces with the different flags are limited to just one trace.

## page_fault_cost
Function tracing of causing a page fault on the different file systems. We use this to identify the call stack for DAX-enabled file systems and comparing differences between ext4-DAX and xfs-DAX.
We measure the cost of page faults by mapping a 4GiB file into memory, and accessing the first byte of different pages in the mapping in random order. The one byte access is traced on the following file systems: ext4, ext4-DAX, xfs, xfs-DAX, NOVA, and an anonymous mmap (with MAP_SHARED flag and MAP_PRIVATE flag).
