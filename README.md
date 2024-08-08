# POPROX Repository Template

This is a template for POPROX source repositories using [`copier`][copier].

[copier]: https://copier.readthedocs.io/en/stable/

## Updating

To *update* a repo already connected to the template, run:

```console
hatch run meta:update-template
```

You can also run `copier` directly:

```console
copier update
```

After updating, review the changes and resolve conflicts (incompatible changes
in the base template and the project source will appear as Git merge conflicts).

## Creating

To create a *new* project from the template, run:

```console
copier copy https://github.com/CCRI-POPROX/poprox-repo-template poprox-new-project
```

It will prompt you with a few questions to initialize the repository.  The project
name should be the same as the name of the repository, and will also be the name
of the Python distribution that the repository will build.

## Maintenance

When we need new capabilities — post-commit hooks, `.gitignore` entries, etc. —
that are likely to be useful across POPROX, it is better to add them to the
template and then update the repositories, so that each repository's deviation
from the base configuration is minimal.  This makes our repositories more
consistent between each other and makes it easier for developers to move between
aspects of the project.

However, if there are changes that are specific to a repository, like new
dependencies, make those directly in the repository and let Copier's merge logic
handle future updates.