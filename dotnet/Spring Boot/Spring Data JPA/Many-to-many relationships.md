
```
@Entity
class Student {
    @Id
    Long id;
    
    @ManyToMany
    Set<Course> likedCourses;
}

@Entity
class Course {

    @Id
    Long id;

    @ManyToMany
    Set<Student> likes;
}
```