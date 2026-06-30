Extension members enable you to "add" methods to existing types without creating a new derived type.

### `this` modifier
You add the `this` modifier to the first parameter of a static method to indicate that the method appears as a member of an instance of the parameter type:
```
public static UserDto ToDto(this AppUser user, ITokenService tokenService)
{
	return new UserDto
	{
		Id = user.Id,
		DisplayName = user.DisplayName,
		Email = user.Email,
		Token = tokenService.CreateToken(user)
	};
}
```