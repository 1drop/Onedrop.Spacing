# Onedrop.Spacing

Add space to any content element on the page.

## Setup

```
composer require 'onedrop/spacing'
```

Add the `Onedrop.Spacing:Mixin.Spacing` mixin to any nodetype that you would want to link to.

E.g. this code will add such ability to every Content nodetype:

```yaml
'Neos.Neos:Content':
  superTypes:
    'Onedrop.Spacing:Mixin.Spacing': true
```

Add the `Onedrop.Spacing:SpaceWrapperBefore` and ``Onedrop.Spacing:SpaceWrapperAfter`` processor to the same nodetype renderer to insert an anchor tag with the given id before it.

E.g.:

```
prototype(Neos.Neos:Content) {
    @process.prependSpace = Onedrop.Spacing:SpaceWrapperBefore
    @process.appendSpace = Onedrop.Spacing:SpaceWrapperAfter
}

prototype(Neos.Neos:ContentComponent) {
    @process.prependSpace = Onedrop.Spacing:SpaceWrapperBefore
    @process.appendSpace = Onedrop.Spacing:SpaceWrapperAfter
}
```

To enable the styles set this is your `Settings.yaml`

```
Onedrop:
  Spacing:
    includeStyles: true
```
