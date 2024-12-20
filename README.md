# Dockerfile Bug: Incorrect Use of CMD

This repository demonstrates a common mistake in Dockerfiles: the incorrect usage of the `CMD` instruction.  The example Dockerfile uses `CMD` to define the main process, but this is problematic when you want to run additional commands along side the defined `CMD`.

**Problem:**

The `CMD` instruction, when used alone, will be overridden when a user runs a Docker container with additional command-line arguments. To fix this, use `ENTRYPOINT` to define the main process and let the user provide additional arguments that will extend the process's execution. 

**Solution:** 

Replace the `CMD` instruction with `ENTRYPOINT`. The `CMD` instruction can still be used for additional arguments to be passed to the main process, allowing flexibility. 