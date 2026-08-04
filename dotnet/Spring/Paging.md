
```
Pageable pageable = PageRequest.of(page, size);
Page<Entry> pageEntry =  entryRepo.findAll(pageable);
List<EntryResponse> entryList = pageEntry.
                stream().
                map(entry -> entryResMaper.apply(entry))
                .toList();
        return new PagedResponse<>(entryList,
                                   pageEntry.getNumber(),
                                   pageEntry.getSize(),
                                   pageEntry.getTotalElements(),
                                   pageEntry.getTotalPages(),
                                   pageEntry.isLast());
```
