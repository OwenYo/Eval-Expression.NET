## Evaluate, Compile and Execute C# code and expression at runtime##

*From simple C# math expression...*
```csharp
int result = Eval.Execute<int>("X + Y", new { X = 1, Y = 2});
```
*To complex code to parse.*
```csharp
int result = Eval.Execute<int>(@"
	var list = new List<int>() { 1..100 };
	var filter = list.Where(x => x < 3);
	return result.Sum(x => x);");
```

> Drastically improve C# reflection performance and lisibility by using Eval Expression.NET.

## Download
**_Stable version available on December 01 2015_**

<a href="https://www.nuget.org/packages/Z.Expressions.Eval/" target="_blank" alt="download nuget"><img src="https://img.shields.io/nuget/v/Z.Expressions.Eval.svg?style=flat-square" /></a>
<a href="https://www.nuget.org/packages/Z.Expressions.Eval/" target="_blank" alt="download nuget"><img src="https://img.shields.io/nuget/dt/Z.Expressions.Eval.svg?style=flat-square" /></a>

```
PM> Install-Package Z.Expressions.Eval
```
*FREE Version limited to 50 characters

## Eval.Execute
**Evaluate and execute the code or expression.**

**Support:**

_Anonymous Class_

```csharp
// using Z.Expressions; // Don't forget to include this.
int result = Eval.Execute<int>("X + Y", new { X = 1, Y = 2});
```

_Argument Position_

```csharp
// using Z.Expressions; // Don't forget to include this.
int result = Eval.Execute<int>("{0} + {1}", 1, 2);
```

_Class Member_

```csharp
// using Z.Expressions; // Don't forget to include this.
dynamic expandoObject = new ExpandoObject();
expandoObject.X = 1;
expandoObject.Y = 2;
int result = Eval.Execute<int>("X + Y", expandoObject);
```

_Extension Methods_

```csharp
// using Z.Expressions; // Don't forget to include this.
string s = "X + Y";
int result = s.Eval<int>(new { X = 1, Y = 2 });
```
**[Learn more](https://github.com/zzzprojects/Eval-Expression.NET/wiki/Eval-Execute)**

## Eval.Compile
**Compile the code or expression and return a delegate.**

**Support:**

*Custom Delegate*
```csharp
// using Z.Expressions; // Don't forget to include this.
var compiled = Eval.Compile<Func<int, int, int>>("X + Y", "X", "Y");
foreach(var item in list)
{
	int result = compiled(item.Value1, item.Value2);
}
```

*Extension Methods*
```csharp
// using Z.Expressions; // Don't forget to include this.
string s = "X + Y";
var compiled = s.Compile<Func<int, int, int>>("X", "Y");
foreach(var item in list)
{
	int result = compiled(item.Value1, item.Value2);
}
```
**[Learn more](https://github.com/zzzprojects/Eval-Expression.NET/wiki/Eval-Compile)**

## What's supported?
The Eval Expression.NET support all C# Syntax:
- All C# Keywords ([MSDN Documentation](https://msdn.microsoft.com/en-us/library/x53a06bb.aspx))
- All C# Operators ([MSDN Documentation](https://msdn.microsoft.com/en-CA/library/6a71f45d.aspx))
- Constant Folding
- Extension Methods
- Generic Type
- Lambda Expression
- Number Suffix

You can even access to C# 6.0 features even if you are using C# 4.0.
- string interpolation
- typename
- null conditional member access

**[Learn more](https://github.com/zzzprojects/Eval-Expression.NET/wiki/Syntax-Supported)**

## FREE vs PRO
Every month, a new monthly trial of the PRO Version is available to let you evaluate all its features without limitations.

Features | FREE Version | [PRO Version](http://eval-expression.net/#pro)
------------ | :-------------: | :-------------:
Maximum Characters | 50 | Unlimited
Commercial License | No | Yes
Royalty-Free | No | Yes
Support & Upgrades (1 year) | No | Yes
Learn more about the **[PRO Version](http://eval-expression.net/#pro)**

## Support
Contact our outstanding customer support for any request. We usually answer within the next business day, hour, or minutes!

- [Website](http://eval-expression.net/)
- [Documentation](https://github.com/zzzprojects/Eval-Expression.NET/wiki)
- [Forum](https://zzzprojects.uservoice.com/forums/327759-eval-expression-net)
- sales@zzzprojects.com

## More Projects
  - [NET Entity Framework Extensions](http://www.zzzprojects.com/products/dotnet-development/entity-framework-extensions/)
  - [NET Bulk Operations](http://www.zzzprojects.com/products/dotnet-development/bulk-operations/)
  - [Eval Expression.NET](https://github.com/zzzprojects/Eval-Expression.NET)
  - [Eval SQL.NET](https://github.com/zzzprojects/Eval-SQL.NET)
  - [Extension Methods Library](https://github.com/zzzprojects/Z.ExtensionMethods/)

