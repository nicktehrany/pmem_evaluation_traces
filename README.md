# Function Traces - "Evaluating Performance Characteristics of the PMDK Persistent Memory Software Stack"

These are all the different traces mentioned throughout my BSc Thesis. All traces were collected using ftrace (<https://elinux.org/Ftrace>).

## mmap_cost
Function tracing of calling ```mmap``` on the different file systems to identify if page table entries are set up on the function call, and if so how many.

## page_fault
Function tracing of causing a page fault on the different file systems. We use this to identify the call stack for DAX-enabled file systems and comparing differences between ext4-DAX and xfs-DAX.
