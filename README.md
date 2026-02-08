# I2EKF-LO to HDMapping simplified instruction

## Step 1 (prepare data)
Download the dataset `reg-1.bag` by clicking [link](https://cloud.cylab.be/public.php/dav/files/7PgyjbM2CBcakN5/reg-1.bag) (it is part of [Bunker DVI Dataset](https://charleshamesse.github.io/bunker-dvi-dataset)).

File 'reg-1.bag' is an input for further calculations.
It should be located in '~/hdmapping-benchmark/data'.


## Step 2 (prepare docker)
```shell
mkdir -p ~/hdmapping-benchmark
cd ~/hdmapping-benchmark
git clone https://github.com/MapsHD/benchmark-I2EKF-LO-to-HDMapping.git --recursive
cd benchmark-I2EKF-LO-to-HDMapping
git checkout Bunker-DVI-Dataset-reg-1
docker build -t i2ekf-lo_noetic .
```

## Step 3 (run docker, file 'reg-1.bag' should be in '~/hdmapping-benchmark/data')
```shell
cd ~/hdmapping-benchmark/benchmark-I2EKF-LO-to-HDMapping
chmod +x docker_session_run-ros1-i2ekf-lo.sh
cd ~/hdmapping-benchmark/data
~/hdmapping-benchmark/benchmark-I2EKF-LO-to-HDMapping/docker_session_run-ros1-i2ekf-lo.sh reg-1.bag .
```

## Step 4 (Open and visualize data)
Expected data should appear in ~/hdmapping-benchmark/data/output_hdmapping-faster-lio
Use tool [multi_view_tls_registration_step_2](https://github.com/MapsHD/HDMapping) to open session.json from ~/hdmapping-benchmark/data/output_hdmapping-faster-lio.

You should see following data

lio_initial_poses.reg

poses.reg

scan_lio_*.laz

session.json

trajectory_lio_*.csv

## Movie
[[movie]](https://youtu.be/B2358Gn62Ho)

## Contact email
januszbedkowski@gmail.com