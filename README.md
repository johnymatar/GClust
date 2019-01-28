# GClust
GClust is a package for divergent nucleotide sequences clustering. Contrarely to traditional clustering methods that focuses on the speed of clustering highly similar sequences, GClust uses a Machine Learning Gaussian Mixture Model and targets the clustering accuracy of divergent sequences with the best possible speed.
The current version of GClust uses Edgar, R.C.'s MUSCLE module (www.drive5.com) for sequences alignment.

# Installation on Linux
- Get the installation package from the Linux folder in our repository "svn checkout https://github.com/johnymatar/GClust/trunk/Linux"
- Extract the compressed package and go to the extracted directory from the console
- Run the following commands: "./configure", "make"
- Run the following command as a sudoer: "make install"
- You can now call "gclust" from anywhere with the desired arguments
- For parallel computation call "mpigclust"
- To use the graphical interface, install mono and then run the command "mono guigclust.exe"

# Usage without installation on Linux
- Get the files ("gclust", "mpigclust", "guigclust.exe", "gclustGMM", and "muscle") from the folder "Linux"
- Put them together in a same directory and browse to that directory from the console
- Call "gclust" with the desired arguments from there. In case the executable "gclust" does not run on your system, just rebuild it from the source gclust.cpp using the command "mpic++ gclust.cpp -o gclust"
- For parallel computation call "mpigclust"
- To use the graphical interface, install mono and then run the command "mono guigclust.exe"

# Usage without installation on M.S. Windows
- As a prerequisite, install Python 2.7 along with its following libraries: numpy, matplotlib, scikit-learn, scipy, cogent, BioPython
- Download the files from the folder "Windows"
- Put them together in a same directory, go to that directory from the command line
- Call "gclust" with the desired arguments from there
- For parallel computation call "mpigclust"
- For a graphical interface run "guigclust.exe"

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
