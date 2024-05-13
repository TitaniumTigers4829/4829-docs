---
description: This is a tutorial for various basic system control
---

# General Programming stuff

[Link ](https://github.com/Mars1523/FRC-Vendor-Libraries)to how to install libraries on WPILib VS code



Solenoids:

* Class: DoubleSolenoid
  * Import:&#x20;
    * `import edu.wpi.first.wpilibj.DoubleSolenoid;`
  * Initialization:
    * `DoubleSolenoid solenoid = new DoubleSolenoid(PneumaticsModuleType.CTREPCM, forwardChannel, reverseChannel);`
  * Usage:&#x20;
    * Extend:
      * `solenoid.set(DoubleSolenoid.Value.kForward);`
    * Retract:
      * `solenoid.set(DoubleSolenoid.Value.kReverse);`

Motors:

* Classes: WPI\_TalonFX, WPI\_TalonSRX
  * Mechanical-speak: Falcon/Falcon 500
  * Programming speak: WPI\_TalonFX
  * Mechanical-speak: Any other CTRE motor type (it will be connected to a talon SRX controller)
  * Programming speak: WPI\_TalonSRX
* Imports:
  * `import com.ctre.phoenix.motorcontrol.can.WPI_TalonFX;`
  * `import com.ctre.phoenix.motorcontrol.can.WPI_TalonSRX;`
* Initialization:
  * `WPI_TalonFX motorFX = new WPI_TalonFX(motorPort);`
  * `WPI_TalonSRX motorSRX = new WPI_TalonSRX(motorPort);`
* Usage (for both):
  * Speed:
    * `motorFX.set(speed);`
    * `motorSRX.set(speed);`
* Built-in PID:
  * Setup:
    * `motorFX.config_kP(0, kP); //kP being the P value`
    * `motorSRX.config_kP(0, kP); //kP being the P value`
    * `// other PID values are config_kI, config_kD, and config_kF.`
* Usage:
  * `public void setDesiredMotorDegree(double degree) {` &#x20;
  * &#x20;`int motorPosFX = (int) ((2048 / 360) * degree);`&#x20;
  * &#x20;`motorFX.set(ControlMode.MotionMagic, motorPosFX);`&#x20;
  * &#x20;`int motorPosSRX = (int) ((2048 / 360) * degree);`
  * &#x20;`motorSRX.set(ControlMode.MotionMagic, motorPosSRX);}`
  * The TalonFX and TalonSRX motor encoders record data **2048** **units per revolution**. The function `.getSelectedSensorPosition()` will return the encoder’s position since it was last reset. The encoder is not constrained to **0-2048**.
    * We don't need to think about this anymore, since with phoenix v6, CTRE units changed to pure rotations as opposed to the # of pulses per full revolution.\


[Limelight](https://docs.limelightvision.io/en/latest/networktables\_api.html)

* Class:&#x20;
  * NetworkTableInstance to get the table with data
  * NetworkTableEntry to get the individual data bits
* Imports:
  * `import edu.wpi.first.networktables.NetworkTableEntry;`
  * `import edu.wpi.first.networktables.NetworkTableInstance;`
* Initialization:
  * `NetworkTableInstance limelight = NetworkTableInstance.getDefault().getTable("limelight").getInstance(); // gets the table with limelight values`
  * `NetworkTableEntry targetX = limelight.getEntry("tx"); // target x position, like a coordinate plane with (0, 0) at the center of the frame`
*   Usage:

    * `public double getTargetX() {`
    * &#x20;`return targetX.getDouble(0.0); // parameter is the value to be returned if there is no target`
    * &#x20;`// tV can also be used to get if there are valid targets in the frame`
    * `}`

    PID: [more in-depth link](https://docs.wpilib.org/en/stable/docs/software/advanced-controls/controllers/pidcontroller.html)
