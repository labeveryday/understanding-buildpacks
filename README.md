# understanding-buildpacks

This is a repo to learn how to use python buildpacks

Buildpack gives you the ability to not have to worry about building a docker file.

Buildpacks are a standard created by cloudfoundry

1. Build your app

    ```python
    print("Hello World!")
    ```

2. Install buildpack tool to build the containers from buildpack

    https://buildpacks.io/docs/tools/pack/

3. Verify the version

    ```bash
    pack --version
    ```

4. Create the default builder for packeto

    ```bash
    pack config default-builder paketobuildpacks/builder:full
    ```

5. Create `Profile` and add your app there.

    `web: python hello.py`

6. Build your app using a python build pack

    ```bash
    pack build myapp --buildpack paketo-community/python@0.4.1
    ```

7. Run your app with docker

    `docker run myapp`

8. To find build packs

    `https://registry.buildpacks.io/searches/python`

## Notes

Pass in your env... III. Config https://12factor.net/config

You dont have to worry about doing the dockerfile configuration

The build pack will automatically grab the `Procfile`, `buildpack.yml`, `requirements.txt`

Here's a sample buildpack: https://github.com/paketo-community/python/tree/main/integration/testdata/pip
