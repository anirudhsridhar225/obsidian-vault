
### Aim: implement cudaMalloc/cudaFree interception and tracking system

i have to override the runtime functions of cuda and track thread-safe allocations. this means that my tracking itself shouldn't take more than a core of cpu compute so that the application doesn't end up lagging to hell and back.

### TODO:
- [ ] LD_PRELOAD mechanism working
- [ ] all cuda allocations are intercepted
- [ ] metadata is automatically updated on malloc/free
- [ ] error handling for allocation failures
- [ ] integration tests with real applications

### LD_PRELOAD
it is an env var in unix os' that lets users specify shared libraries to be loaded before other libraries, including std system libraries like `libc`.