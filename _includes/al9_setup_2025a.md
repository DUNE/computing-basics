~~~
# find a spack environment and set it up
# setup spack   

# this is for spack v1.2.2
echo "setup-prototype.sh"
. /cvmfs/dune.opensciencegrid.org/spack/setup-env.sh
spack env activate dune-prototype
echo "Activated dune-prototype"

echo "load GCC so don't use system"
echo "GCC"
spack load gcc@12.5.0 arch=linux-almalinux9-x86_64_v2 # need v2 for very old cpu

# access some disks
export DUNEDATA=/exp/dune/data/users/$USER
export DUNEAPP=/exp/dune/app/users/$USER
export PERSISTENT=/pnfs/dune/persistent/users/$USER
export SCRATCH=/pnfs/dune/scratch/users/$USER
~~~
{: .language-bash}

You can check your environment by doing this

~~~
# test-paths.sh
echo "which root"
which root
root --version
echo "which gcc"
which gcc
gcc --version
echo "which python"
which python
python --version
echo "which cmake"
which cmake
cmake --version
~~~
{: .language-bash}
