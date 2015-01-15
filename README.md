#AddMVCModuleDynamic
##A very simple version of how to make ASP.NET MVC modular

This mvc web application template demostrate how you can dynamic add mvc projects to your main web mvc application.

With this example, you can have distributed team that one team work one MVC project 1 + all the backend domain and database access.
one team work another MVC project 2 with the different backend projects.

When you build and deploy is very simple, you just build solution then all the mvc project will go to the main web mvc project.
and when deploy the main web project, the application will grap the files and deploy too.


##Key Points
+  Main MVC project has no reference to other MVC projects
+  *.pubxml is the key file need to edit when publish
+  Each module mvc project need to add following command after build
    +  xcopy /E /Y /D "$(ProjectDir)Views" "$(SolutionDir)MainWeb\Views"
    +  xcopy /E /Y /D "$(ProjectDir)Scripts" "$(SolutionDir)MainWeb\Scripts"
    +  xcopy /E /Y /D "$(ProjectDir)Content" "$(SolutionDir)MainWeb\Content"

##Things need to watch out
+ Need to becareful use the dll version between projects.
+ Have not tested during build will bring all module mvc project's referenced dll
+ Not support for DI, Ioc module yet.




