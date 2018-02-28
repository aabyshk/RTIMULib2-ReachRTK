# RTIMULib2-ReachRTK

This is a refactoring of the RTIMULib2 (https://github.com/richardstechnotes/RTIMULib2) for using on the Reach RTK GPS. At this point it supports only display of the fused pose, and filtered acceleration and gyroscope values.

### How to build
* Connect the Reach RTK to your local wi-fi network or through ethernet-over-USB
* SSH into the device: ssh root@[IP Address]; Password: emlidreach
* Run the following commands:

      git clone https://github.com/aabyshk/RTIMULib2-ReachRTK
      cd RTIMULib2-ReachRTK/
      mkdir build
      cd build/
      cmake ..
      make -j4 && make install

### Test the IMU Output
You can test whether the IMU is working or not by running the RTIMULibDrive executable. As a part of my tests, I did some calibration using the RTIMULibCal tool. The configuration file RTIMULib.ini from my test is in the root folder of the repo which is configured to work with MPU-9250 IMU on the SPI 5.1 port of the Emlid Reach RTK GPS. I cannot guarantee if this would give good results with your device. Copy the RTIMULib.ini to build/RTIMULibDrive folder.

Run the following commands to display the fused pose, acceleration and gyro values:

      ./RTIMULibDrive

This is a work in progress, so may not work for everyone.
