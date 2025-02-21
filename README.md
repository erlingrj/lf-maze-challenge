# LF Maze Challenge

## Requirements
- Linux (teste with Ubuntu 24.04)
- macOS (tested with )
- A C compiler such as `gcc` or `clang`
- A recent version of `cmake`

## Getting started

### All platforms
#### Install LFC
```sh
curl -Ls https://install.lf-lang.org | bash -s cli
```

### Linux/Ubuntu

### Gazebo simulator
Following the guide [here](https://gazebosim.org/docs/harmonic/install_ubuntu/), 
install Gazebo Harmonic with:
```sh
sudo apt-get update
sudo apt-get install curl lsb-release gnupg
sudo curl https://packages.osrfoundation.org/gazebo.gpg --output /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/gazebo-stable.list > /dev/null
sudo apt-get update
sudo apt-get install gz-harmonic
```

### Eigen

```sh
sudo apt libeigen3-dev
```


### MacOS

#### Gazebo simulator
```sh
brew tap osrf/simulation
brew install gz-harmonic
```

#### Eigen
```sh
brew install eigen
```

### Verify installations

1. Lingua Franca Compiler
```sh
lfc --version
lfc src/HelloWorld.lf
bin/HelloWorld
```


2. Gazebo
```sh
gz sim --version
gz sim models/model.sdf
```

Press the "Play" button in the lower left corner.

In another terminal run:

```sh
gz topic -e -t /lidar --json-output
```

This should flood the terminal with LiDAR scan messages.
