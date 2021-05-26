# understanding-buildpacks
This is a repo to learn how to use python buildpacks

Buildpack gives you the ability to not have to worry about building a docker file.

1. Install buildpack tool to build the containers from buildpack

    https://buildpacks.io/docs/tools/pack/

2. Verify the version

    ```bash
    pack --version
    ```

3. Create the default builder for packeto

    ```bash
    pack config default-builder paketobuildpacks/builder:full
    ```

4. Create `Profile` and add your app there.

    `web: python hello.py`

5. Build your app using a python build pack

    ```bash
    pack build myapp --buildpack paketo-community/python@0.4.1
    ```

6. Run your app with docker

    `docker run myapp`

7. To find build packs

    `https://registry.buildpacks.io/searches/python`