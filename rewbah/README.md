# Good practices for Older Adults

## Authors
- Shyam Ravichandran
- Denise Geisskovitck
- Sébastien Mosser
- Anne-Marie Pinna-Déry


## Recruiting Older Adults (McMaster)

### Off-the-shelf recruitment strategies

#### Phone

<div align="center">

![](figures/phone.svg)

</div>

#### Poster display

<div align="center">

![](figures/posters.svg)

</div>

#### On-site recruitment

<div align="center">

![](figures/trusted.svg)

</div>

### Assembling a recruitment strategy

```
composition {
    justification recruitement is assemble(phone, posters, trusted) {
        conclusion: "Potential participant pool is large enough"
        strategy: "Combining recruitments methods"
    }
}
```

<div align="center">

![](figures/recruitement.svg)

</div>

### Refining how to access to phone numbers

#### Re-using an existing phone directory


<div align="center">

![](figures/existing_directory.svg)

</div>

```
composition {
    justification phone_reuse is refine(phone, existing_directory) {
        hook: "phone:directory"
    }
}
```
<div align="center">

![](figures/phone_reuse.svg)

</div>


#### Building one from scratch

<div align="center">

![](figures/build_directory.svg)

</div>

```
composition {
    justification phone_reuse is refine(phone, existing_directory) {
        hook: "phone:directory"
    }
}
```
<div align="center">

![](figures/phone_build.svg)

</div>

### Refining how to access to locations

<div align="center">

![](figures/locations.svg)

</div>

### Complete justification

```
composition {

    justification recruitement is assemble(phone, posters, trusted) {
        conclusion: "Potential participant pool is large enough"
        strategy: "Combining recruitments methods"
    }

    justification temp is refine(recruitment, locations) {
        hook: "loc_available"
    }

    justification final is refine(temp, phone_reuse) {
        hook: "directory"
    }

}
```

<div align="center">

![](figures/recruitement_final.svg)

</div>