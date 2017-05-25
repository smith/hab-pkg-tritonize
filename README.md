# hab-pkg-tritonize

Create a [Triton Infrastructure
Container](https://docs.joyent.com/images#infrastructure-containers) custom
image that includes specified Habitat packages set up to run on the Habitat
supervisor.

Given these options:

* A "primary" package identifier
* A list of optional additional package identifiers
* A source image name
* Optional additional supervisor arguments
* Optional additional service arguments

Do the following:

* Create a Triton Infrastructure Container instance from the given source image name
* Wait for the container to be ready
* On the instance:
  * Install Habitat
  * Create a `hab` user
  * Install an initscript for the Habitat Supervisor
  * Load the specified services
* Create an image from the instance
* Wait for the image to be ready
* Destroy the prototype instance
* Print information about the new image

You can then create instances based on those images that will run your services.

## Usage

Run

```
hab pkg exec smith/hab-pkg-tritonize hab-pkg-tritonize [OPTIONS] PKG_IDENT
```
