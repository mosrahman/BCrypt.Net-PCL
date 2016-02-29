# BCrypt.NET
BCrypt.Net is a Universal Encryption(Blowfish) utility for Windows, Universal Windows Application, Windows IoT Core, Store Application, Phone, Asp.Net Web Application and Xamarin.

# How to use it
Add reference to your code like this.

`using BCrypt.Net;`
`using BCrypt = BCrypt.Net.BCrypt;`

To hash a password for the first time, call the `HashPassword()` method with a random salt, like this:

`string pass =  global::BCrypt.Net.BCrypt.HashPassword("password", global::BCrypt.Net.BCrypt.GenerateSalt());`

To check whether a plaintext password matches one that has been hashed previously, use the `CheckPassword()` method:

`if (global::BCrypt.Net.BCrypt.CheckPassword("password", pass)) {`
`Console.WriteLine("Match");`
`} else {`
`Console.WriteLine("Don’t Match");`
`}`

The `GenerateSalt()` method takes an optional integer parameter that determines the computational complexity of the hashing:

`string SaltStrong30 = global::BCrypt.Net.BCrypt.GenerateSalt(30);`
`string SaltStrong31 = global::BCrypt.Net.BCrypt.GenerateSalt(31);`

The amount of work increases exponentially (2**number). The default number is 10, and the valid range is 4 to 31.


