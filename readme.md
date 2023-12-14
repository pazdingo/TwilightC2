# Twilight C2 

## Overview

Twilight C2 is a closed-source, lightweight SSH C2 written in Golang. This tool is designed for executing custom commands in the TermFX format and attacks thru APIs. Twilight C2 operates without allowing remote devices to connect and receive custom commands, focusing on local execution and security. It provides a straightforward and direct method for command execution through APIs on the host system.


## Features

- **Custom Commands:** Execute commands in the TermFX format on the local host system.

## Configuration Files

1. **`assets/server.json`:**
   - This file contains configuration settings for the Twilight C2 server, including network details and other server-specific parameters.

2. **`assets/roles.json`:**
   - Define user roles and access permissions in this file. Customize user privileges for secure access control to Twilight C2.

3. **`assets/attacks/apis.json`:**
   - Store API commands in this file. Customize API endpoints and parameters for specific command functionalities.

4. **`assets/attacks/groups.json`:**
   - Define groups for organizing API commands. Customize parameters and settings for specific command groups.

## Custom Commands

Custom commands are defined in the TermFX format and can be added to the `assets/commands` directory. Each command file should have the `.tfx` extension.

### Example Command File (`assets/commands/example_command.tfx`):

```tfx
Name=test
Description=Hello there
Permissions=["vip+","vip"]
==== BODY START ====
<?swash
var gradient = require("gradient")
var color = gradient.new()
color.AppendRGB(255,0,0)
color.AppendRGB(255,255,255)
color.SetText("Hello World, you're a vip/vip+ user!")
printf("%s", color.Execute())
?>
```

## Installation

1. **Download the Application:**
   - Obtain the Twilight C2 binary from the official website or a trusted source.

2. **Configure Settings:**
   - Edit the relevant configuration files (`server.json`, `roles.json`, `apis.json`, `groups.json`) in the `assets` directory to customize Twilight C2 according to your requirements.

3. **Add Custom Commands:**
   - Create custom command files in the `assets/commands` directory using the `.tfx` format.

4. **Run the Application:**
   - Execute the Twilight C2 binary on your server.
   - chmod +x twilight
   - screen -S twilight ./twilight

## Usage

- **User Authentication:**
  - Create user accounts and define roles using the `roles.json` file for secure access control.

- **Executing Custom Commands:**
  - Run the Twilight C2 binary on the local host to execute custom commands in the TermFX format.

## License

Twilight C2 is distributed as a closed-source application. Please refer to the terms of use provided with your copy of the software for licensing details.

## Support and Contact

For support or inquiries, please contact the Twilight C2 support team on telegram @twilightcnc.

---

**Note:** This is a non profit C2. Updates will come randomly.