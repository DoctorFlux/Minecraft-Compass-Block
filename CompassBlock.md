﻿
## **Compass Block ComputerCraft Integration Guide**

The Compass Block is a unique block in Minecraft that stores and displays positional and directional data. Integrated with ComputerCraft, it allows users to access and modify its information programmatically, enhancing automation and interaction within the game.

Below is a guide on its available methods for ComputerCraft.
---

### Table of Contents

| Method                                           | Description                                                                                   |
|--------------------------------------------------|-----------------------------------------------------------------------------------------------|
| [`getSavedName()`](#getsavedname)                | Returns the `SavedName` property of the Compass Block.                                      |
| [`setSavedName(name)`](#setsavednamename)        | Sets the `SavedName` property of the Compass Block.                                           |
| [`getFacingDirection()`](#getfacingdirection)    | Returns the direction the Compass Block is facing.                                               |
| [`getDimensionName()`](#getdimensionname)        | Returns the ID of the dimension where the Compass Block is located.                        |
| [`getX()`](#getx)                                | Returns the X coordinate of the Compass Block.                                               |
| [`getY()`](#gety)                                | Returns the Y coordinate of the Compass Block.                                               |
| [`getZ()`](#getz)                                | Returns the Z coordinate of the Compass Block.                                               |

Below is a ComputerCraft Lua program that demonstrates how to interact with the Compass Block using the available methods:

```lua
local side = "top"
local compassBlock = peripheral.wrap(side)

while true do
    print("\nChoose an option:")
    print("1. Set Name")
    print("2. Get Name")
    print("3. Get Coordinates (X, Y, Z)")
    print("4. Get Facing Direction")
    print("5. Get Dimension Name")
    print("6. Exit")

    local choice = read()
    if choice == "1" then
        print("Enter the name for the Compass Block:")
        local name = read()
        compassBlock.setSavedName(name)
        print("Name set!")
    elseif choice == "2" then
        local name = compassBlock.getSavedName()
        print("The Compass Block's name is: " .. name)
    elseif choice == "3" then
        local x = compassBlock.getX()
        local y = compassBlock.getY()
        local z = compassBlock.getZ()
        print("The Compass Block's coordinates are: X=" .. x .. ", Y=" .. y .. ", Z=" .. z)
    elseif choice == "4" then
        local direction = compassBlock.getFacingDirection()
        print("The Compass Block is facing: " .. direction)
    elseif choice == "5" then
        local dimension = compassBlock.getDimensionName()
        print("The Compass Block is in the dimension: " .. dimension)
    elseif choice == "6" then
        break
    else
        print("Invalid choice!")
    end
end
```
### **getSavedName()**
**Description:** Fetches the `SavedName` property of the Compass Block.
- **Returns:** The current `SavedName` as a string.
- **Example Usage:**
  ```lua
	local compassBlock = peripheral.wrap("right")
	local name = compassBlock.getSavedName()
	print("The Compass Block's name is: " .. name)
### **setSavedName(name)**

**Description:** Sets the `SavedName` property of the Compass Block.
- **Parameters:**  
  - `name`: A string denoting the desired name for the Compass Block.  
- **Returns:** A confirmation message: "Saved name set!".
- **Example Usage:**
  ```lua
  local compassBlock = peripheral.wrap("right")
  compassBlock.setSavedName("NewNameByComputercraft")
### **getFacingDirection()**
**Description:** Obtains the direction the Compass Block faces.
- **Returns:** A string indicating the direction (e.g., "up", "down", "north", "south", "east", or "west").
- **Example Usage:**
  ```lua
	local compassBlock = peripheral.wrap("right")
	local direction = compassBlock.getFacingDirection()
	print("The Compass Block is facing: " .. direction)
### **getDimensionName()**
**Description:** Finds the ID of the dimension in which the Compass Block resides.
**Returns:** A string indicating the dimension ID.
- **Example Usage:**
  ```lua
	local compassBlock = peripheral.wrap("right")
	local dimension = compassBlock.getDimensionName()
	print("The Compass Block is in the dimension: " .. dimension)
### **getX()**
**Description:** Retrieves the X coordinate of the Compass Block
- **Returns:** The X coordinate as a number.
- **Example Usage:**
  ```lua
	local compassBlock = peripheral.wrap("right")
	local x = compassBlock.getX()
	print("The Compass Block's X coordinate is: " .. x)

### **getY()**
**Description:** Retrieves the Y coordinate of the Compass Block
- **Returns:** The Y coordinate as a number.
- **Example Usage:**
  ```lua
	local compassBlock = peripheral.wrap("right")
	local x = compassBlock.getY()
	print("The Compass Block's Y coordinate is: " .. x)

### **getZ()**
**Description:** Retrieves the Z coordinate of the Compass Block
- **Returns:** The Z coordinate as a number.
- **Example Usage:**
  ```lua
	local compassBlock = peripheral.wrap("right")
	local x = compassBlock.getZ()
	print("The Compass Block's Z coordinate is: " .. x)
