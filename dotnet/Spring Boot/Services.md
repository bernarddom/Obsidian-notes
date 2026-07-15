### Interfaces
```
public interface EntryService {
    Entry addEntry(EntryRequest req);

    PagedResponse<EntryResponse> getEntries(int page, int size);

    EntryResponse getEntryById(Integer id);
}
```

### Implementations

```
@Service
public class EntryServiceImpl implements EntryService {
	@Override
    public Entry addEntry(EntryRequest req) {
        Entry entry = entryReqMaper.apply(req);
        return entryRepo.save(entry);
    }
}
```