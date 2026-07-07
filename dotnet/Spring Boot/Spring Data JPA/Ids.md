```
@Id
@SequenceGenerator(
	name = "brand_id_sequence",
    sequenceName = "brand_id_sequence"
)
@GeneratedValue(
    generator = "brand_id_sequence",
    strategy = GenerationType.SEQUENCE
)
private Integer id;
```