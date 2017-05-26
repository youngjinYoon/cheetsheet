How to run Matlab on Docker environment 

With SSH, we can open Matlab but without GUI !
If you want to use Matlab with GUI, you should connect to Remote connection


Run docker: docker run --rm -v /tmp/.X11-unix:/tmp/.X11-unix:ro -e DISPLAY=$DISPLAY -v "$MATLAB_ROOT":/usr/local/MATLAB/from-host -v "$MATLAB_LOGS":/var/log/matlab --mac-address="$MATLAB_MAC_ADDRESS" 

You should install matlab dependencies"

apt-get update && apt-get install -y \
    libpng12-dev libfreetype6-dev \
    libblas-dev liblapack-dev gfortran build-essential xorg


"$MATLAB_LOGS" : Optional 



How to get Mac address:
run "idconfg" copy mac address from eht0:HWaddr, it is form of 00:00:00:00

From https://hub.docker.com/r/ninjaben/matlab-support/~/dockerfile/