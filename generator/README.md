make_template is a script to create CycleCloud cluster templates. The use-case is the creation of cluster templates based on a couple of simple architecture choices, without having to dig into learning and setting up a cluster template manually.
For now the implemented functionality is:

- choosing a scheduler: pbspro, gridengine or slurm
- setting up multiple nodearrays: extending the default execute with scheduler dependent identifier (now only pbspro) 
- add mounting a NFS export from a CycleCloud NFS filer for homedirs or projectdata
- add mounting Azure Netapp Files (ANF) for e.g. homedirs or projectdata 


Example use:

'''./make_template --name mycluster --scheduler pbspro --anf projects'''

This will result in a template file mycluster.txt which can be imported using:

'''cyclecloud import_template -f mycluster.txt'''

The cluster above will have pbspro as its scheduler, have a single nodearray called execute and on the "External Filesystems" tab, you can specify the mount details for ANF.
