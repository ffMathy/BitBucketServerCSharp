[![Build status](https://ci.appveyor.com/api/projects/status/75jvf8viifojh6j6/branch/master?svg=true)](https://ci.appveyor.com/project/jlouros/bitbucketservercsharp/branch/master)

[![NuGet](https://img.shields.io/nuget/v/BitBucketServerCSharp.svg)](https://www.nuget.org/packages/BitBucketServerCSharp/)


Bitbucket Server API wrapper for .Net Core
============================================================================

.Net Core C# API wrapper for Atlassian Bitbucket Server
For more information about Bitbucket Server visit: https://www.atlassian.com/software/bitbucket/server
API documentation can be found here: https://developer.atlassian.com/bitbucket/server/docs/latest/


##Sample Usage

	// BitBucket client connection using basic authentication
	var client = new BitBucketApiClient("http://your_bitbucket_server_url:7990/", "username", "password");

	//Gets a list of projects (by default a maximum of 25 results will be return)
	// we recommend use of async/await instead of forcing synchronous execution
	var projects = client.Projects.Get().Result;

	//Gets a list of repositories from project "PROJKEY" (by default a maximum of 25 results will be return)
	// using async
	var repositories = await client.Repositories.Get("PROJKEY");

	//Delete repository "REPOSLUG" from project "PROJKEY"
	await client.Repositories.Delete("PROJKEY", "REPOSLUG");


*Take a look at the integration tests project for more samples.*

