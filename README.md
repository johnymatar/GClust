# GClust
GClust is a package for divergent nucleotide sequences clustering. Contrarely to traditional clustering methods that focuses on the speed of clustering highly similar sequences, GClust uses a Machine Learning Gaussian Mixture Model and targets the clustering accuracy of divergent sequences with the best possible speed.
The current version of GClust uses Edgar, R.C.'s MUSCLE module (www.drive5.com) for sequences alignment.

# Installation on Linux
- Get the installation files from the "Linux/Install" folder in our repository "svn checkout https://github.com/johnymatar/GClust/trunk/Linux/Install" (subversion package is needed to use "svn": as a sudoer, run "apt-get install subversion").
- Browse to the download directory: "cd Install"
- Run the following commands: "chmod 777 configure", "./configure", "make"
- Run the following command as a sudoer: "make install"
- You can now call "gclust" from anywhere with the desired arguments
- For parallel computation call "mpigclust"
- To use the graphical interface, install mono (run "apt install mono-runtime" as a sudoer) and then call "guigclust"

# Usage without installation on Linux
- Get the files from the "Linux/Standalone" folder in our repository "svn checkout https://github.com/johnymatar/GClust/trunk/Linux/Standalone" (subversion package is needed to use "svn": as a sudoer, run "apt-get install subversion").
- Keep them together in a same directory and browse to that directory from the console: "cd Standalone"
- For the first use ONLY: fix the executables properties by running the command "chmod 777 * "
- Call "gclust" with the desired arguments from there
- For parallel computation call "mpigclust" with the desired arguments
- To use the graphical interface, install mono (run "apt install mono-runtime" as a sudoer) and then call "guigclust"

# Usage without installation on M.S. Windows
- As a prerequisite, install Python 2.7 along with its following libraries: numpy, matplotlib, scikit-learn, scipy, cogent, BioPython
- Download the files from the "Windows" folder in our repository
- Put them together in a same directory, go to that directory from the command line
- Call "gclust" with the desired arguments from there
- For parallel computation call "mpigclust"
- For a graphical interface run "guigclust"

# Integration into Galaxy
Follow the instructions in the README file in the Galaxy folder

# Current version features
- Test for alignment failure
- Parallel computation for the distance matrix using MPI.
- Checking the presence of all required modules and files prior run
- Supports arguments by using -mdist -in -out -alignMode -gapOpen -gapExtend for gclust:
 available mdist are EDNAFULL, BLOSUM62, and PAM250
 available alignMode are: fast, moderate, maxPrecision
- Calls LaplacianAndGMM from python sub-module gclustGMM.py on Windows
- LaplacianAndGMM python sub-module is converted to gclustGMM executable on Linux for easier use
- Runs, via the executable, from anywhere from the original directory without the need of environment variables. Needs all the dependent file to be present in its directory (gclust, mpigclust, muscle executable, and gclustGMM)
- Can enable figures displaying from the python sub-module.
- Compatible for Galaxy integration
