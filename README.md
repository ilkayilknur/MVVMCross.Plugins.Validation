Validation Plug-in for MVVMCross
--------------------------------
The usage is simple:
```
var errors = Mvx.Resolve<IValidator>().Validate(YourViewModelObj);
if (!errors.IsValid)
{
       //TODO: You can display the errors there.
       return;
}
```
Of course, you must do RegistType in 'APP.cs':
```
public class App : MvvmCross.Core.ViewModels.MvxApplication
{
    public override void Initialize()
    {
        CreatableTypes()
            .EndingWith("Service")
            .AsInterfaces()
            .RegisterAsLazySingleton();
            
        Mvx.RegisterType<IValidator, Validator>();  //Regist IValidator
        
        RegisterAppStart<ViewModels.FirstViewModel>();
    }
}
```
Read about more usage here http://agiescode.ghost.io/2014/05/10/mobile-project-one/


- 2015/5/12 Added iOS and Android Support
- 2015/5/13 Nuget support https://www.nuget.org/packages/MVVMCross.Plugins.Validation/
- 2016/4/09 Added FieldBinding Support

Unfortunately, do to the way PCLs behave, I couldn't roll in any other validation libraries. I am sure it is possible, I ran into a wall and needed to back some stuff out, so I created a new annotation framework :p.


MVVMCross.Plugins.Validation is distributed under
------------------------------------------------

Microsoft Public License (MS-PL)

This license governs use of the accompanying software. If you use the software, you
accept this license. If you do not accept the license, do not use the software.

1. Definitions
The terms "reproduce," "reproduction," "derivative works," and "distribution" have the
same meaning here as under U.S. copyright law.
A "contribution" is the original software, or any additions or changes to the software.
A "contributor" is any person that distributes its contribution under this license.
"Licensed patents" are a contributor's patent claims that read directly on its contribution.

2. Grant of Rights
(A) Copyright Grant- Subject to the terms of this license, including the license conditions and limitations in section 3, each contributor grants you a non-exclusive, worldwide, royalty-free copyright license to reproduce its contribution, prepare derivative works of its contribution, and distribute its contribution or any derivative works that you create.
(B) Patent Grant- Subject to the terms of this license, including the license conditions and limitations in section 3, each contributor grants you a non-exclusive, worldwide, royalty-free license under its licensed patents to make, have made, use, sell, offer for sale, import, and/or otherwise dispose of its contribution in the software or derivative works of the contribution in the software.

3. Conditions and Limitations
(A) No Trademark License- This license does not grant you rights to use any contributors' name, logo, or trademarks.
(B) If you bring a patent claim against any contributor over patents that you claim are infringed by the software, your patent license from such contributor to the software ends automatically.
(C) If you distribute any portion of the software, you must retain all copyright, patent, trademark, and attribution notices that are present in the software.
(D) If you distribute any portion of the software in source code form, you may do so only under this license by including a complete copy of this license with your distribution. If you distribute any portion of the software in compiled or object code form, you may only do so under a license that complies with this license.
(E) The software is licensed "as-is." You bear the risk of using it. The contributors give no express warranties, guarantees or conditions. You may have additional consumer rights under your local laws which this license cannot change. To the extent permitted under your local laws, the contributors exclude the implied warranties of merchantability, fitness for a particular purpose and non-infringement.
