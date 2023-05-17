ros2_vosk_msgs
======================

Custom messages for speech-to-text services based on [Vosk](https://github.com/alphacep/vosk-api)

Extracted from the ROS1 package [ros_vosk](https://github.com/alphacep/ros-vosk)
These messages are required for the ROS2 version [ros2_vosk](https://github.com/redchillipadi/ros2_vosk)

## Tutorials

1. Install this package to your ros2 workspace

  ```bash
  mkdir -p ~/ros2_ws/src 
  cd ~/ros2_ws/src
  git clone https://github.com/redchillipadi/ros2_vosk_msgs
  cd ..
  colcon build
  ```
  
2. Source the messages before using them

  ```bash
  source install/setup.bash
  ros2 topic info speech_recognition/vosk_result
  ```

## Interface

### Publishing Topics
* speech_recognition/vosk_result    -> vosk_node.py publishes a custom "speech_recognition" message
* speech_recognition/final_result   -> vosk_node.py publishes a simple string with the final result
* speech_recognition/partial_result -> vosk_node.py publishes a simple string with the partial result
* tts/status -> tts_engine.py publishes the state of the engine. True if it is speaking False if it is not. If the status is true vosk_node won't process the audio stream so it won't listen to itself 
* tts/phrase -> tts_engine.py subscribes to this topic in order to speak the given string. Name your desire and it shall be heard by all in the room..

## Author
Angelo Antikatzidis <an.antikatzidis@gmail.com>
Nickolay V. Shmyrev <nshmyrev@gmail.com>
Adrian Grigo <agrigo2001@yahoo.com.au>
