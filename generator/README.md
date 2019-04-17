make_template is a script to create CycleCloud cluster templates. The use-case is the creation of cluster templates based on a couple of simple architecture choices, without having to dig into learning and setting up a cluster template manually.
For now the implemented functionality is:

- choosing a scheduler: pbspro, gridengine or slurm
- setting up multiple nodearrays: extending the default execute with scheduler dependent identifier (now only pbspro) 
- add mounting a NFS export from a CycleCloud NFS filer for homedirs or projectdata
- add mounting Azure Netapp Files (ANF) for e.g. homedirs or projectdata 
