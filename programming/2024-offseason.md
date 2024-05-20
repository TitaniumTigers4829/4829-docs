---
description: Offseason bobot code structure
---

# 2024 Offseason

IO - interface used by the \<Mechanism>IO\<Hardware/Sim> class for input AutoLogging.

Hardware - generally deals with configs (PID, soft limits, signals and stuff).

Sim - class used by the physics sim when simulating robot code, useful for testing if code conceptually works.

Subsystem - create functions for running the mechanism, used in commands.\


* Flywheel
  * Main Subsystem
  * IO
    * Hardware&#x20;
    * Sim
* Elevator
  * Main Subsystem
  * IO
    * Hardware&#x20;
    * Sim
* Pivot
  * Main Subsystem
  * IO
    * Hardware
    * Sim
* Intake
  * Main Subsystem
  * IO
    * Hardware
    * Sim
* Vision
  * Main Subsystem
  * IO
    * Hardware
    * Sim (photon)
* Swerve
  * Main Drive (Combines module & gyro info)
  * GyroIO:
    * Hardware (NavX)
    * Sim
  * (Swerve) Module
    * ModuleIO:
      * Hardware (TalonFX)
      * Sim
  * Odom thread
