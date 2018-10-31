# GClust
GClust is a package for divergent nucleotide sequences clustering. Contrarely to traditional clustering methods that focuses on the speed of clustering highly similar sequences, GClust uses a Machine Learning Gaussian Mixture Model and targets the clustering accuracy of divergent sequences with the best possible speed.
The current version of GClust uses Edgar, R.C.'s MUSCLE module (www.drive5.com) for sequences alignment.

# Current version features
- Test for alignment failure | 
- Parallel computation for the distance matrix using MPI. Serial if the number of processes is equal to 1 | 
- Chequing the presence of all required modules and files on run | 
- Supports arguments by using -mdist -in -out -alignMode -gapOpen -gapExtend for gclust:
 available mdist are EDNAFULL, BLOSUM62, and PAM250 | 
 available alignMode are: fast, moderate, maxPrecision
- Calls LaplacianAndGMM from python sub-module gclust-GMM.py on Windows | 
- LaplacianAndGMM python sub-module is converted to gclust-GMM executable on Linux for easier use | 
- Runs, via the executable, from anywhere from the original directory without the need of environment variables. Needs all the dependent file to be present in its directory (muscle executable and gclust-GMM) | 
- Can enable figures displaying from the python sub-module. | 
- Compatible for Galaxy integration

# Usage without installation
For both Linux and Windows, just put the executable files together in a same directory, go to that directory from the console or command line, and call "gclust" with the desired arguments from there. In case the executable "gclust" does not run on your system, just rebuild it from the source gclust.cpp using the command "mpic++ gclust.cpp -o gclust".

# Installation on Linux
- Get the installation package from our repository "wget https://github.com/johnymatar/GClust/raw/master/gclust-31.10.18.tar.gz" | 
- Extract the compressed package and go to the extracted directory from the console
- Run the following commands: "./configure", "make" | 
- Run the following command as a sudoer: "make install" | 
- You can now call "gclust" from anywhere with the desired arguments.
