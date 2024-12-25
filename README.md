# shadcn-registry-starter

CLI tool to generate [shadcn](https://ui.shadcn.com/) compatible registries.

## Installation

```bash
npm install shadcn-registry-starter
```

## Building The Registry

1. Create a registry file. Registry files should be in JSON format and validate against the [registry schema](./src/registry/registry.schema.ts). You can find examples in the [examples](./examples) directory. You can also use the [`generate`](#generate-registry) command to generate a new registry (currently experimental).

2. Build the registry:
    ```bash
    npx shadcn-registry-starter build <path-to-registry>
    ```

    ## Options

    - `-p, --path <path>`: The path to output the registry files.
    - `-i, --index <path>`: The path to output the registry index file.
    - `--index-include <types...>`: The types to include in the registry index file. Can be one or more of `ui`, `hook`, `lib`.

3. Et voilà! Your registry files are now ready to be used with shadcn CLI.


## CI/CD

You can use shadcn-registry-starter in your CI/CD pipeline to automatically generate your registry files.

```json
"scripts": {
    "build:registry": "npx shadcn-registry-starter@latest build <path-to-registry>"
}
```


## Generate registry

The `generate` command is currently experimental.

To generate a new registry, run the `generate` command with the path to the folder containing your components.

```bash
npx shadcn-registry-starter@latest generate <path-to-components>
```

This will generate a new registry file in the same folder as your components, under a file called `index.json`.
So if you run `npx shadcn-registry-starter@latest generate ./components`, you will find the generated registry file at `./components/index.json`.


