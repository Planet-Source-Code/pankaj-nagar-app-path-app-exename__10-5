<div align="center">

## App\.Path & App\.EXEName


</div>

### Description

As .Net does Not include App object as in VB here is a solution for App.Path and App.ExeName
 
### More Info
 
Just add this class in your application and use it

App.Path and App.EXEName


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Pankaj Nagar](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/pankaj-nagar.md)
**Level**          |Beginner
**User Rating**    |4.3 (30 globes from 7 users)
**Compatibility**  |VB\.NET
**Category**       |[System Services/ Functions](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/system-services-functions__10-23.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/pankaj-nagar-app-path-app-exename__10-5/archive/master.zip)





### Source Code

```
Option Explicit
Option Strict
Imports System
Imports System.IO
Class ThisApp
	Private mAppPath As String
	Private mExeName As String
	Public ReadOnly Property AppPath() As String
		Get
			Return mAppPath
		End Get
	End Property
	Public ReadOnly Property ExeName() As String
		Get
			Return mExeName
		End Get
	End Property
	Public Sub New()
		Dim p As Path
		Try
			mAppPath = System.Reflection.Assembly.GetExecutingAssembly.Location
			mExeName = Dir(mAppPath)
			mAppPath = p.GetFullPath((Left(mAppPath, (Len(mAppPath) - Len(mExeName)))))
		Catch
			MsgBox(Err.Description, MsgBoxStyle.Critical, "Error!")
		End Try
	End Sub
End Class
Module modMain
	Sub Main()
		Dim MyApp As ThisApp = New ThisApp()
		MsgBox(MyApp.AppPath, MsgBoxStyle.Information, "App Path")
		MsgBox(MyApp.ExeName, MsgBoxStyle.Information, "Exe Name")
	End Sub
End Module
```

