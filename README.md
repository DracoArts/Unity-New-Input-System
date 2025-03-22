
# Welcome to DracoArts
![Logo](https://dracoarts-logo.s3.eu-north-1.amazonaws.com/DracoArts.png)



# Unity's New Input System

Unity's New Input System is a modern, flexible, and highly customizable input handling system designed to replace Unity's legacy input system (UnityEngine.Input). It provides a more robust and scalable way to manage player input across a wide range of devices, including keyboards, mice, gamepads, touchscreens, and more. The New Input System was introduced to address the limitations of the legacy system and to better support modern game development needs, such as cross-platform input, rebindable controls, and complex input handling

# Key Features of the New Input System
 ## 1. Device-Agnostic Input Handling: 
The New Input System abstracts input devices into a common interface, making it easier to handle input from multiple devices (e.g., keyboard, gamepad, touch) without writing device-specific code.

Supports a wide range of input devices, including:

- Keyboard and mouse

- Gamepads (Xbox, PlayStation, Nintendo Switch, etc.)

- Touchscreens

- VR/AR controllers

- Joysticks and steering wheels

 - Custom HID devices
## 2.Input Actions and Action Maps: 
Inputs are organized into Actions and Action Maps:

- Actions: Represent specific inputs (e.g., "Jump", "Move", "Shoot").

- Action Maps: Groups of actions that define a context (e.g., "Gameplay", "Menu").

Actions can be bound to multiple input sources (e.g., "Jump" can be triggered by the spacebar, a gamepad button, or a touchscreen tap).

 ## 3.Rebindable Controls: 
 Players can remap controls at runtime, allowing for customizable input schemes.

 This is particularly useful for accessibility and player preference.

 ## 4. Composite Bindings: 
Complex inputs (e.g., 2D movement using WASD or a gamepad stick) can be handled using composite bindings.

Examples include:

 - 2D Vector: Combines inputs for up/down/left/right.

- Button with One Modifier: Combines a button press with a modifier key (e.g., Shift + Click).

## 5.Input Processors and Interactions:
- Processors: Modify raw input data (e.g., normalize stick values, invert axes).

- Interactions: Define how inputs are interpreted (e.g., tap, hold, double-tap, slow/fast tap).

## 6. Cross-Platform Support:

The New Input System simplifies cross-platform development by automatically handling differences between input devices and platforms.

Developers can create platform-specific overrides if needed.


# How the New Input System Works

 ## 1.Input Action Asset:

The core of the New Input System is the Input Action Asset, which defines all the actions, action maps, and bindings for your project.

This asset can be created and edited using the Input Action Editor in the Unity Editor.

 ## 2.Input Actions:

Actions represent specific player inputs (e.g., "Jump", "Move").

Each action can have multiple bindings (e.g., "Jump" can be bound to the spacebar, a gamepad button, or a touchscreen tap).

## 3.Binding Paths:

Bindings specify the actual input source (e.g., <Keyboard>/space, <Gamepad>/buttonSouth).

Binding paths use a standardized format to reference input devices and controls.

## 4.Input Action Events:

Actions trigger events such as:

- started: When the input is first detected.

- performed: When the input is completed (e.g., a button press).

- canceled: When the input is canceled (e.g., a button release).

## 5.Reading Input Values:

Actions can return input values (e.g., a float for an axis, a Vector2 for a stick, or a bool for a button).

Example: Vector2 movement = moveAction.ReadValue<Vector2>();

# Setting Up the New Input System
## 1.Install the Package:

The New Input System is available via Unity's Package Manager.

Go to Window > Package Manager, search for "Input System", and install it.

## 2.Enable the New Input System:

In Edit > Project Settings > Player, under Active Input Handling, select "Both" or "Input System (Preview)".

Restart Unity to apply the changes.

## 3.Create an Input Action Asset:

Right-click in the Project window and select Create > Input Actions.

Open the Input Action Editor to define actions, action maps, and bindings.

 ## 4.Use Input Actions in Code:

Reference the Input Action Asset in your scripts.
## Usage/Examples
     private Vector2 _input;
    private CharacterController _characterController;
    private Vector3 _direction;

    [SerializeField] private float speed;

    private void Awake()
    {
        _characterController = GetComponent<CharacterController>();
    }

    private void Update()
    {
        _characterController.Move(_direction * speed * Time.deltaTime);
    }

    public void Move(InputAction.CallbackContext context)
    {
        _input = context.ReadValue<Vector2>();
        _direction = new Vector3(_input.x, 0.0f, _input.y);
    }
## Images

![](https://raw.githubusercontent.com/AzharKhemta/DemoClient/refs/heads/main/Unity%20New%20%20Input%20System.gif)

## Authors

- [@MirHamzaHasan](https://github.com/MirHamzaHasan)
- [@WebSite](https://mirhamzahasan.com)


## 🔗 Links

[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/mir-hamza-hasan/posts/?feedView=all/)
## Tech Stack
**Client:** Unity,C#

**Package:** Input System




## Documentation

[Documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.7/manual/index.html/)

