TinyHttp - a tiny C# HTTP server

Copyright (C) 2012 Matt Jamieson

```c#
public class Program : RequestProcessor
{
    public Program()
    {
        Get["/"] = s => new HtmlResponse("<h1>Welcome</h1>");
        Get["/hello/{name}"] = s => new HtmlResponse(String.Format("<h1>Hello, {0}</h1>", s.name));
    }

    public static void Main()
    {
        var host = new TinyHttpHost("http://localhost:9999/", new Program());
        host.Start();

        while (true) ;
    }
}
```