# Vulkan's Extension Mechanism
One thing Khronos APIs are brilliant at doing is allowing Vulkan implementations to extend the normal functionality of Vulkan, and add new techniques & features to the Vulkan API independently of the rest of the API and other implementations. For example, when NVIDIA's RTX platform launched it was the first platform to feature real-time raytracing en masse alongside typical graphics workloads like Vulkan. Of course, because NVIDIA was the first to allow raytracing with Vulkan, they had to create a specially-made extension (called VK_NV_ray_tracing) to add this missing functionality.

If lots of Vulkan drivers support a given extension (as anyone can implement any Vulkan extension provided it conforms with the original author's intentions), the vendors involved will often work together to make an multi-vendor extension, which are prefixed with EXT (for generic multi-vendor) or KHR (for extensions authored by the Khronos Group). If a KHR extension sees widespread adoption, Khronos will often promote an extension into the core specification as part of a new Vulkan version, allowing it to be used anywhere where that specific verison of Vulkan is supported. An example of this would be VK_KHR_get_physical_device_properties2 being promoted and included as part of Vulkan 1.1.

If the hardware and graphics driver supports using new features defined in extensions, it will allow the developer to enable & use them. Each graphics card only supports a specific set of extensions, and they must be queried and enabled explicitly before accessing them. You can visualize like so:

```
if (VK_KHR_extension_name)
{
    // use the new cool features!
}
else
{
    // do things the old way...
}
```

Obviously it's not that simple to check if an extension is supported, but keep that visualization in your head - we'll expand upon it with actual code later. For now, all you need to know is that some drivers can extend Vulkan with custom functionality through "extensions", which you can then query and enable to use that functionality. 