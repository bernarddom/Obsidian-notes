It is recommended to use the `@ManyToOne` unless necessary
```
@Entity
@Table(name="CART")
public class Cart {
    @OneToMany(mappedBy="cart")
    private Set<Item> items;	
}
```

```
@Entity
@Table(name="ITEMS")
public class Item {
    @ManyToOne
    @JoinColumn(name="cart_id", nullable=false)
    private Cart cart;

    public Item() {}
}
```