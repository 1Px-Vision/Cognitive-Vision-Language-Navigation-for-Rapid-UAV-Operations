# Cognitive-Vision-Language-Navigation-for-Rapid-UAV-Operations

In GPS-denied environments, a cognitive drone for search-and-rescue missions can interpret high-level human instructions and transform them into actionable navigation decisions in real time. Using an LLM navigation framework, the UAV allows operators to issue free-form commands such as “go to the far corridor, then approach the victim,” even under time pressure and in unfamiliar, cluttered environments. Rather than treating navigation as a pure text-generation problem, the cognitive drone performs 2D spatial grounding, linking semantic instructions directly to visual regions in its first-person RGB view. Through this process, the vision–language model incrementally converts ambiguous commands into grounded 2D waypoint cues, which are then combined with estimated travel distance to produce 3D motion commands for the UAV.

![](https://github.com/1Px-Vision/Cognitive-Vision-Language-Navigation-for-Rapid-UAV-Operations/blob/main/LLM_Agent_0.jpg)

LLM-guided multi-agent UAV navigation scenario with three cooperative drones: a leader, a left follower, and a right follower. The top row shows the onboard camera views of each agent, while the middle row presents their individual HUDs with flight status, clearance, RMSE, and control mode. The bottom panel displays the swarm scenario map, including the planned path, executed trajectories, and relative formation behavior. In this example, the agents maintain coordinated navigation under a shared safe-mode policy, while the leader drives the mission and the followers adapt their motion to preserve formation and avoid obstacles. This setup highlights how LLM-based decision support can improve cooperative tracking, situational awareness, and robust multi-agent navigation in cluttered environments.

![](https://github.com/1Px-Vision/Cognitive-Vision-Language-Navigation-for-Rapid-UAV-Operations/blob/main/LLM_Multi-Agent_3.jpg)

### Hit: You ran the wslconfig command-line program, not the .wslconfig settings file. Microsoft documents .wslconfig as a text file in your Windows user profile that applies global WSL settings, while WSL management commands are handled through wsl.exe; Microsoft also notes those old management options were consolidated into wsl.

Do this in Windows PowerShell or CMD:
````
notepad %UserProfile%\.wslconfig
````
Paste this:
````
[wsl2]
networkingMode=mirrored
firewall=true
dnsTunneling=true
autoProxy=true
````
Then save the file. The file must be named exactly .wslconfig, not .wslconfig.txt. Microsoft says networkingMode=mirrored is configured under [wsl2] in .wslconfig, and that mirrored mode is available on Windows 11 22H2 and later.

Then restart WSL completely:
````
wsl --shutdown
wsl --status
````
After reopening Kali/Ubuntu, test again:
````
ip addr
ip route
nc -vz 192.168.137.10 22
ssh ubuntu@192.168.137.10
````
## Hybrid AI–FPGA Architecture

Python-based drone simulation and control framework that combines a Language Agent, Agent-level DQN decision making, and FPGA-accelerated drone emulation over a TCP communication link. The system is designed for GPS-denied autonomous navigation, where the simulated drone operates inside a virtual environment while perception, planning, and control are coordinated between software intelligence and hardware-assisted emulation.

At the core of the architecture, a task prompt is processed by a Language Agent that integrates an LLM with a DQN-based decision layer to generate high-level navigation and control actions. These actions are exchanged with an external FPGA-based drone emulation model, enabling fast hardware-assisted computation and realistic closed-loop interaction. On the simulator/control host, the framework provides real-time monitoring through multiple visual scopes, including a GPS-denied visual-inertial navigation view, front navigation camera, front-depth perception, and an online front-depth SLAM map.

![](https://github.com/1Px-Vision/Cognitive-Vision-Language-Navigation-for-Rapid-UAV-Operations/blob/main/FPGA_Sim.jpg)

This platform is intended for research and development in:

* Autonomous drone navigation.
* GPS-denied visual-inertial SLAM.
* LLM-guided robotic decision making.
* Reinforcement learning for control.
* FPGA/KRIA-based hardware acceleration.
* Real-Time simulation and human-interpretable monitoring.



