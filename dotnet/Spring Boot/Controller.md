
### Examples
```
    @PostMapping
    private ResponseEntity<Brand> saveBrando(
            @Valid @RequestBody Brand brand){
        return ResponseEntity.ok().body(brandService.saveBrand(brand.getName()));
    }

    @GetMapping
    private ResponseEntity<List<Brand>> getBrandsByName(
            @RequestParam(required = false) String name
                                                       ){
        List<Brand> brands;
        if (name != null && !name.isBlank()){
            brands = brandService.getBrandsByNameLike(name);
        }
        else {
            brands = brandService.getAllBrands();
        }
        return ResponseEntity.ok().body(brands);
    }
```

#### @RequestMapping
```
@RestController  
@RequestMapping("/api/venue")  
public class VenueController {  
	...  
}
```