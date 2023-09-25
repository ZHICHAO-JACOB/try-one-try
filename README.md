# try-one-try
To use or test the ShuttleCar, you should firstly go to this folder in terminal:
cd ~/AutoStore/ShuttleCarControl/ShuttleCarControl/build

Start ShuttleCar Serve:
./tester 3

Start ShuttleCar's finger controller:
./tester 0
Enter 1 and the shuttle's finger will lift up (upright)
Enter 1 and the finger on the shuttle will be lowered (horizontal)

Control laser:
./tester

To Control a certain motor, you should firstly go to this folder in terminal:
cd ~/AutoStore/ShuttleCarControl/MotorControl/build

Enter commands in this format to control a certain motor: 
./testerServoCtrl $motor_name $target_position $velocity

motor_name:
      walking: Control the ShuttleCar to drive on the track
      lift: Control the ShuttleCar to rise or fall
      exp: Control the ShuttleCar to pull or push bins
      rot: Control the horizontal rotation of the ShuttleCar

target_position:
      The above four different motors have different limits, so the target_position can't exceed corresponding limits.
      The detailed parameters are in the bincollector.json file

velocity:
      walking: If using the walking motor, velocity should be set to 20.
      lifting: If using the lifting motor, velocity should be set to 50.
      exp: If using the pulling/pushing motor, velocity should be set to 500.
      rot: If using the rotation motor, velocity should be set to 300.

For example, if we want to retract the extended arm of the car, we should enter the command: 
cd ~/AutoStore/ShuttleCarControl/MotorControl/build
./testServoCtrl exp 0 500

