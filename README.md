1. Create `netstandard2.0` class library:
`dotnet new classlib --framework "netstandard2.0" -o KiotaTest`
2. Set `LangVersion` to `7.3` in the csproj file.
3. Add Kiota dependencies:
```
dotnet add package Microsoft.Kiota.Abstractions
dotnet add package Microsoft.Kiota.Http.HttpClientLibrary
dotnet add package Microsoft.Kiota.Serialization.Form
dotnet add package Microsoft.Kiota.Serialization.Json
dotnet add package Microsoft.Kiota.Serialization.Text
dotnet add package Microsoft.Kiota.Serialization.Multipart
```
4. Add file `events-api.yml`.
5. Generate API client.
`kiota generate -l CSharp -c EventsClient -n KiotaEvents.Client -d ./events-api.yml -o ./Client --clean-output`
6. Build.  

Build Output:  
`[...]KiotaTest\Client\Events\EventsRequestBuilder.cs(20,88): error CS0246: The type or namespace name 'DateOnly' could not be found (are you missing a using directive or
an assembly reference?) [...]`
