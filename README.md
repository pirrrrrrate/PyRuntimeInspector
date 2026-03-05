# PyRuntimeInspector
A high-level runtime memory inspector and manipulator for CPython applications.
Traditional reverse engineering tools like IDA Pro or GDB are invaluable for low-level analysis, but they often require tedious assembly-level debugging to decipher high-level application logic.
PyRuntimeInspector bridges this gap by operating directly at the CPython abstraction layer. Instead of wrestling with raw memory addresses and hex dumps, it enables developers to interact with a running process using Python’s native introspection capabilities (e.g., dir(), getattr(), type()). This approach significantly accelerates the research, debugging, and hot-patching process for Python-based applications by treating the target's memory as a live, navigable object tree.
# How it works
1. Launch your target Python application (script, GUI app, PyInstaller/.exe bundle, etc.) — as long as it loads the standard CPython interpreter DLL (python3x.dll).
2. Use some kind of injector to load PyRuntimeInspector.dll into target process, for example System Informer is fine: Right click on process -> Properties -> Modules -> Options -> Load module...
3. Launch PyRepl.exe and pray to god it works I guess. Try print(list(sys.modules.keys())) or just print("123").
