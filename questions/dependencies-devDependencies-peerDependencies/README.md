# Question

## What is the difference between `dependencies`, `devDependencies` and `peerDependencies` in `package.json`?

# YouTube Video

[![youtube thumbnail](http://img.youtube.com/vi/PxJ5wzFPTFU/0.jpg)](http://www.youtube.com/watch?v=PxJ5wzFPTFU "dependencies vs devDependencies vs peerDependencies in package.json YouTube video")

## Answer

### `dependencies`

They are the direct dependencies needed for the package to be used and it's included in the code of the package.

They are installed traversely.

### `devDependencies`

They are only used for development and they are not included in the package.

They are not installed traversely

### `peerDependencies`

They are not included in the package but are expected to be installed by the host package.

If they are not installed by the host, npm will install them.

In case there is a conflict between the host's package version and the plugin's, npm will fire an error.

Try running `npm install --save-dev @vue/test-utils@1` in `vue-app-v3`
