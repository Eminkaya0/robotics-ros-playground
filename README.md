# Robotics ROS Playground

A comprehensive collection of ROS and ROS2 projects focusing on robot navigation, computer vision, and LLM integration. This repository serves as both a learning resource and a showcase of practical robotics applications using the Robot Operating System.

## 📋 Table of Contents
- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Installation](#installation)
  - [ROS](#ros-installation)
  - [ROS2](#ros2-installation)
- [Projects](#projects)
  - [Navigation](#navigation-projects)
  - [Computer Vision](#computer-vision-projects)
  - [LLM Integration](#llm-integration-projects)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [Contributing](#contributing)
- [License](#license)

## 🔍 Overview

This repository contains a collection of projects implemented using both ROS (Robot Operating System) and ROS2. The projects are designed to demonstrate practical applications in robotics, with a focus on:

- **Autonomous Navigation**: Path planning, obstacle avoidance, and SLAM (Simultaneous Localization and Mapping)
- **Computer Vision**: Object detection, tracking, and image processing for robotics
- **LLM Integration**: Using Large Language Models to enhance robot intelligence and interaction capabilities

Each project includes detailed documentation, code explanations, and usage instructions to facilitate learning and experimentation.

## 📁 Repository Structure

```
robotics-ros-playground/
├── navigation/
│   ├── path_planning/
│   ├── obstacle_avoidance/
│   └── slam/
├── vision/
│   ├── object_detection/
│   ├── image_processing/
│   └── tracking/
├── llm/
│   ├── text_to_command/
│   ├── context_awareness/
│   └── interaction/
├── common/
│   ├── utils/
│   └── launch/
└── docs/
    ├── images/
    ├── tutorials/
    └── presentations/
```

## 💻 Installation

### ROS Installation

To install ROS (Noetic for Ubuntu 20.04):

```bash
# Setup sources.list
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

# Setup keys
sudo apt install curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

# Update package index
sudo apt update

# Install ROS
sudo apt install ros-noetic-desktop-full

# Environment setup
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc

# Dependencies
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential

# Initialize rosdep
sudo rosdep init
rosdep update
```

### ROS2 Installation

To install ROS2 (Humble for Ubuntu 22.04):

```bash
# Locale settings
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

# Setup sources
sudo apt install software-properties-common
sudo add-apt-repository universe
sudo apt update && sudo apt install curl
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

# Install ROS2
sudo apt update
sudo apt install ros-humble-desktop

# Environment setup
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc

# Install development tools
sudo apt install ros-dev-tools
```

## 🤖 Projects

### Navigation Projects

Projects related to autonomous navigation:

1. **Basic Path Planning**: Implementation of algorithms like A*, Dijkstra, and RRT
2. **Obstacle Avoidance**: Reactive and predictive methods for avoiding obstacles
3. **SLAM Implementation**: Building maps and localizing robots simultaneously

### Computer Vision Projects

Projects focused on vision-based robotics:

1. **Object Detection**: Using neural networks to detect objects relevant to robotics tasks
2. **Image Processing Pipeline**: Processing raw camera inputs for robot perception
3. **Visual Tracking**: Following objects of interest through a sequence of frames

### LLM Integration Projects

Projects leveraging Large Language Models:

1. **Text to Robot Commands**: Translating natural language into robot actions
2. **Context-Aware Navigation**: Using LLMs to enhance situational understanding
3. **Human-Robot Interaction**: Building conversational interfaces for robots

## 🚀 Usage

Each project contains its own dedicated README with specific usage instructions. General usage pattern:

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/robotics-ros-playground.git
   cd robotics-ros-playground
   ```

2. Build the workspace:
   ```bash
   # For ROS
   catkin_make
   
   # For ROS2
   colcon build
   ```

3. Source the workspace:
   ```bash
   # For ROS
   source devel/setup.bash
   
   # For ROS2
   source install/setup.bash
   ```

4. Run a specific project:
   ```bash
   # Example for running a navigation demo in ROS
   roslaunch navigation path_planning_demo.launch
   
   # Example for running a vision demo in ROS2
   ros2 launch vision object_detection_demo.launch.py
   ```

## 📦 Dependencies

Common dependencies across projects:

- ROS/ROS2 (as described in installation)
- Python 3.8+ with NumPy, OpenCV, TensorFlow/PyTorch
- Navigation stack: `ros-*-navigation`
- Vision libraries: `ros-*-vision-opencv`
- For LLM projects: HuggingFace Transformers, PyTorch

Specific project dependencies are listed in each project's README.

## 🤝 Contributing

Contributions are welcome! If you'd like to contribute:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please ensure your code follows the existing style conventions and includes appropriate documentation.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 📬 Contact

If you have any questions or suggestions, feel free to open an issue or contact me directly.

Happy coding and robot building! 🤖
