# ShuttleCar Control Instructions

This README provides step-by-step instructions on how to setup and control the ShuttleCar.

## Contents

- [Remote Connection](#remote-connection)
- [ShuttleCar Server](#shuttlecar-server)
- [ShuttleCar Finger Controller](#shuttlecar-finger-controller)
- [Laser Control](#laser-control)
- [Motor Control](#motor-control)

## Remote Connection

Firstly, log in to the ToDesk software and remotely connect to the industrial computer on the shuttle using account number `859874814` and password `f7i6q5iq`.

## ShuttleCar Server

To start the ShuttleCar Server, navigate to the `ShuttleCarControl` directory and start the `tester` with the argument `3`:

```bash
cd ~/AutoStore/ShuttleCarControl/ShuttleCarControl/build
./tester 3
```

## ShuttleCar Finger Controller

To control the ShuttleCar's finger, navigate to the `ShuttleCarControl` directory and start the `tester` with the argument `0`. 

```bash
cd ~/AutoStore/ShuttleCarControl/ShuttleCarControl/build
./tester 0
```

- Enter `1` and the shuttle's finger will lift up (upright)
- Enter `1` again and the finger on the shuttle will be lowered (horizontal)

## Laser Control

To control the laser, use the `tester` without arguments:

```bash
./tester
```

## Motor Control

To control a specific motor, navigate to the `MotorControl` directory and use the `./testerServoCtrl` command with the required arguments.

```bash
cd ~/AutoStore/ShuttleCarControl/MotorControl/build
./testerServoCtrl $motor_name $target_position $velocity
```

- `motor_name`: This specifies the motor you want to control. The options are:
  - `walking`: Controls the ShuttleCar to drive on the track
  - `lift`: Controls the ShuttleCar to rise or fall
  - `exp`: Controls the ShuttleCar to pull or push bins
  - `rot`: Controls the horizontal rotation of the ShuttleCar

- `target_position`: This is the desired position for the motor. The parameters for each motor are defined in the `bincollector.json` file.

- `velocity`: This is the speed of the motor. The recommended values for each motor are:
  - `walking`: Set velocity to `20`
  - `lifting`: Set velocity to `50`
  - `exp`: Set velocity to `500`
  - `rot`: Set velocity to `300`

For example, to retract the extended arm of the car, use the following commands:

```bash
cd ~/AutoStore/ShuttleCarControl/MotorControl/build
./testerServoCtrl exp 0 500
```
