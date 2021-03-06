# About Vulkan

Vulkan is an Application Programming Interface (API) specification developed and maintained by the Khronos Group, a consortium of lots of stakeholders in graphics development such as NVIDIA, AMD, Intel, and Arm; and other big names in the industry such as Epic Games and Valve, just to name a few. There are over 100 member organisations in the Khronos Group, and they collectively contribute to build open standards and specifications such as Vulkan.

This is important to note, as Vulkan by itself is not an API - it’s the specification and the driver that together provide the standardized interface to the GPU. The Vulkan specification only specifies the expected behaviour for operations you request and the input that you provide to it. This means it’s up to the driver vendor to choose how to implement the specified behaviour, which can lead to weird quirks between different implementations of Vulkan. You probably won’t come across any of those quirks within this book, as we’ve done our best not to encourage usage of any unspecified behaviour (“unspecified behaviour” being behaviour of a function or operation isn’t defined in the specification).

Usually, Vulkan is implemented by the GPU hardware manufacturers themselves (apart from a few exceptions like Google’s swiftshader, which runs on CPUs), so each graphics card you buy only supports specific versions of Vulkan - the ones that the graphics card’s Vulkan drivers are specifically built for. Therefore, it’s recommended to update your graphics drivers if you are experiencing bugs, because any unconforming behaviour goes against the specification for Vulkan.

Most operating systems allow GPU vendors to provide drivers for Vulkan, however there are some cases (such as on macOS) where the GPU manufacturers can’t provide Vulkan drivers. With macOS, it’s because Apple have their own Metal API, which is built specifically for Apple iPhones and Apple Macs. Luckily, a group called The Brenwill Workshop have developed the open-source (thanks to Valve) Vulkan emulator called MoltenVK which is used to implement Vulkan using Apple’s Metal API as a translation layer.

The Khronos Group publicly hosts all specification documents for all Vulkan versions, which you can find on their GitHub repository linked at the bottom of this page. If you’re interested in grabbing a copy of the Vulkan specification for reading alongside this book, the version we’re using is Vulkan 1.2 which will teach you more about the specifics of Vulkan.

- Vulkan's GitHub: https://github.com/KhronosGroup/Vulkan-Docs
