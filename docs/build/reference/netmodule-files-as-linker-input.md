---
title: "fichiers .netmodule en tant qu’entrée de l’éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adafad3532b17573278e7afd82bc33f2c3c50b67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="netmodule-files-as-linker-input"></a>Fichiers .netmodule en tant qu'entrée de l'Éditeur de liens
Link.exe accepte désormais .obj et .netmodule MSIL en tant qu’entrée. Le fichier de sortie produit par l’éditeur de liens sera un assembly ou un fichier .netmodule sans dépendance d’exécution sur n’importe quel fichier .obj ou .netmodule entrés dans l’éditeur de liens.  
  
 fichiers .netmodule sont créés par le compilateur Visual C++ avec [/LN (créer un Module MSIL)](../../build/reference/ln-create-msil-module.md) ou par l’éditeur de liens avec [/NOASSEMBLY (créer un Module MSIL)](../../build/reference/noassembly-create-a-msil-module.md). fichiers .obj sont toujours créés dans une compilation Visual C++. Pour d’autres compilateurs Visual Studio, utilisez le **/target : module** option du compilateur.  
  
 Dans la plupart des cas, vous devez passer à l’éditeur de liens le fichier .obj de la compilation Visual C++ qui a créé le fichier .netmodule, à moins que le fichier .netmodule a été créé avec [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md). Fichiers .netmodule MSIL utilisés comme entrées dans l’éditeur de liens doivent être MSIL pur, qui peut être produit par le compilateur Visual C++ à l’aide **/CLR : safe**. Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015. Les compilateurs .NET de Visual Studio produisent des modules MSIL pures par défaut.  
  
 Pour plus d’informations sur l’appel de l’éditeur de liens à partir de la ligne de commande, consultez [syntaxe de ligne de commande de l’éditeur de liens](../../build/reference/linker-command-line-syntax.md), [code de génération C/C++ sur la ligne de commande](../../build/building-on-the-command-line.md), et [définir le chemin d’accès et les Variables d’environnement pour Les versions de ligne de commande](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
 Passage à l’éditeur de liens d’un fichier .netmodule ou .dll qui a été compilé par le compilateur Visual C++ avec **/CLR** ou **/CLR : pure** peut provoquer une erreur de l’éditeur de liens. Pour plus d’informations, consultez [choix du Format des fichiers d’entrée .netmodule](../../build/reference/choosing-the-format-of-netmodule-input-files.md).  
  
 L’éditeur de liens accepte les fichiers .obj natifs ainsi que les fichiers .obj MSIL compilés avec **/CLR**, **/CLR : pure**, ou **/CLR : safe**. Lors du passage des fichiers .obj mixtes dans la même version, la vérifiabilité du fichier de sortie résultant, par défaut, est égale au niveau plus bas de vérifiabilité des modules d’entrée. Par exemple, si vous passez un .obj safe et pure à l’éditeur de liens, le fichier de sortie sera pur. [/CLRIMAGETYPE (spécifier Type of CLR Image)](../../build/reference/clrimagetype-specify-type-of-clr-image.md) vous permet de spécifier un niveau inférieur de vérifiabilité, si c’est ce dont vous avez besoin.  
  
 Si vous avez actuellement une application qui est composée de deux ou plusieurs assemblys et que vous souhaitez que l’application doit être contenu dans un assembly, vous devez recompiler les assemblys et lier les fichiers .obj ou .netmodule pour produire un assembly unique.  
  
 Vous devez spécifier un point d’entrée à l’aide [/ENTRY (symbole de Point d’entrée)](../../build/reference/entry-entry-point-symbol.md) lors de la création d’une image exécutable.  
  
 Lors de la liaison avec un fichier .obj ou .netmodule MSIL, utilisez [/LTCG (génération de Code d’édition de liens)](../../build/reference/ltcg-link-time-code-generation.md), sinon lorsque l’éditeur de liens rencontre le MSIL .obj ou .netmodule, il redémarre la liaison avec /LTCG.  
  
 Les fichiers .obj ou .netmodule MSIL peuvent également être passés à cl.exe.  
  
 Fichiers .obj ou .netmodule MSIL d’entrée ne peut pas comporter de ressources incorporées. Une ressource est incorporée dans un fichier de sortie (module ou assembly) avec [/ASSEMBLYRESOURCE (incorporer une ressource gérée)](../../build/reference/assemblyresource-embed-a-managed-resource.md) option de l’éditeur de liens ou avec le **/resource** option du compilateur dans d’autres compilateurs Visual Studio.  
  
 Lorsque vous effectuez la liaison MSIL, et si vous ne spécifiez pas [/LTCG (génération de Code d’édition de liens)](../../build/reference/ltcg-link-time-code-generation.md), vous verrez un message informatif indiquant que la liaison redémarre. Ce message peut être ignoré, mais to améliorer les performances de l’éditeur de liens avec la liaison MSIL, spécifiez explicitement **LTCG**.  
  
## <a name="example"></a>Exemple  
 Dans le code C++, le bloc catch d’un bloc try correspondant sera appelé pour une exception de celles du système. Toutefois, par défaut, le CLR encapsule les exceptions non système avec <xref:System.Runtime.CompilerServices.RuntimeWrappedException>. Lorsqu’un assembly est créé à partir de Visual C++ et les modules non Visual C++ et que vous souhaitez un bloc catch dans le code C++ d’être appelé à partir de sa clause try correspondante lorsque le bloc try lève une exception de celles du système, vous devez ajouter le  
  
 attribut [assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)] pour le code source pour les modules non C++.  
  
```  
// MSIL_linking.cpp  
// compile with: /c /clr  
value struct V {};  
  
ref struct MCPP {  
   static void Test() {  
      try {  
         throw (gcnew V);  
      }  
      catch (V ^) {  
         System::Console::WriteLine("caught non System exception in C++ source code file");  
      }  
   }  
};  
  
/*  
int main() {  
   MCPP::Test();  
}  
*/  
```  
  
## <a name="example"></a>Exemple  
 En modifiant la valeur booléenne de l’attribut WrapNonExceptionThrows, vous modifiez la capacité du code Visual C++ pour intercepter une exception de celles du système.  
  
```  
// MSIL_linking_2.cs  
// compile with: /target:module /addmodule:MSIL_linking.obj  
// post-build command: link /LTCG MSIL_linking.obj MSIL_linking_2.netmodule /entry:MLinkTest.Main /out:MSIL_linking_2.exe /subsystem:console  
using System.Runtime.CompilerServices;  
  
// enable non System exceptions  
[assembly:RuntimeCompatibility(WrapNonExceptionThrows=false)]  
  
class MLinkTest {  
   public static void Main() {  
      try {  
         MCPP.Test();  
      }  
      catch (RuntimeWrappedException) {  
         System.Console.WriteLine("caught a wrapped exception in C#");  
      }  
   }  
}  
```  
  
```Output  
caught non System exception in C++ source code file  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers d’entrée LINK](../../build/reference/link-input-files.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)