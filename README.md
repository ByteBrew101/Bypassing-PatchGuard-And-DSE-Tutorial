# Bypassing-PatchGuard-And-DSE-Tutorial
Now CodeForge.io has a bypass for this, but there are multiple ways to do so via a KeBugCheckEx hook, Using a EFI bootkit and patching the kernel image before KiSystemStartup is called (PG is initialized before ntoskrnl.exe main entrypoint aka KiSystemStartup is initialized)

Bootkit is not recommended because its a very detected approach and you would require to turn SB off which alot of anticheats like Vanguard enforce (TPM, HVCI, VBS, SB) and EfiGuard is detected by the instruction
```cpp
int 20h
```


To bypass DSE you could set g_CiOptions in CI.dll to 0 which.. isn't too hard because you can hook KeBugCheckEx, flip the CR0.WP bit and then quickly set it back scott free, CodeForge.io does it differently

- Wrriten by GvhVisor, will write a PoC soon.

For educational purposes
