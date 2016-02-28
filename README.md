BCrypt.NET
BCrypt.NET is a Universal Encryption utility implementing the Blowfish. It works on various platforms like Desktop Application, ASP.NET Application, Windows Universal Application for Windows Store, Phone and Windows IoT Core.
How to use it
Add reference to your code like this
using Sozasoft.BCrypt;

To hash a password for the first time, call the HashPassword() method with a random salt, like this:

string pass =  BCrypt.HashPassword("password" BCrypt.GenerateSalt());

To check whether a plaintext password matches one that has been hashed previously, use the CheckPassword() method:

if (BCrypt.CheckPassword("password", pass)) {
Console.WriteLine("Match");
} else {
Console.WriteLine("Don’t Match");
}

The GenerateSalt() method takes an optional integer parameter that determines the computational complexity of the hashing:
string SaltStrong10 = BCrypt.GenerateSalt(10);
string SaltStrong12 = BCrypt.GenerateSalt(12);

The amount of work increases exponentially (2**number), so each increment is twice as much work. The default number is 10, and the valid range is 4 to 31.


