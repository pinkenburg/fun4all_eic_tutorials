This Tutorial shows how to convert event generator output to root files which 
can be read by Fun4All. The event generator output has to be readable by 
eic-smear.

The ConvertFile.C ROOT macro uses BuildTree() from eic-smear to convert the 
event generator output to a root file with a common format. The macro defaults 
to the provided Milou file MILOU_5x100_TOTAL_01_20evt.out, converting all 
events (Nevents=0)

Usage:

root.exe

.x ConvertFile.C("<file>",<Nevents>);

The root file is named after the inputfile. The Fun4All_EIC_Generator_Display.C
reads the root file simulates the particles traveling through air in a 1.5T 
solenoidal field. The macro defaults to the root file 
MILOU_5x100_TOTAL_01_20evt.root which is generated by running ConvertFile.C with
the default arguments

root.exe

.x Fun4All_EIC_Generator_Display.C("<rootfile>")

This shows the first event, if you want to see subsequent events use

Fun4AllServer *se = Fun4AllServer::instance();
se->run(1);

and 

se->run(1);

for all subsequent events
