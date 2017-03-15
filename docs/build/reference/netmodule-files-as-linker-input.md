---
title: "Fichiers .netmodule en tant qu&#39;entr&#233;e de l&#39;&#201;diteur de liens | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".netmodules"
  - "liaison (C++), modules"
  - "modules, Visual C++"
  - "liaison MSIL"
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fichiers .netmodule en tant qu&#39;entr&#233;e de l&#39;&#201;diteur de liens
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

link.exe reçoit désormais le .obj MSIL et le .netmodules comme entrée.  Le fichier de sortie produit par l'éditeur de liens est un assembly ou un .netmodule sans dépendance au moment de l'exécution sur l'un des .obj ou des .netmodules qui ont été mis en entrée de l'éditeur de liens.  
  
 Les fichiers .netmodules sont créés par le compilateur Visual C\+\+ avec [\/LN \(Créer le module MSIL\)](../../build/reference/ln-create-msil-module.md) ou par l'éditeur de liens avec [\/NOASSEMBLY \(Créer un module MSIL\)](../../build/reference/noassembly-create-a-msil-module.md). Les fichiers .obj sont toujours créés dans une compilation Visual C\+\+.  Pour d'autres compilateurs Visual Studio, utilisez l'option du compilateur **\/target:module**.  
  
 Dans la plupart des cas, vous devez passer à l'éditeur de liens le fichier .obj de la compilation Visual C\+\+ qui a créé le .netmodule, à moins que le .netmodule ait été créé avec [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  Les .netmodule MSIL utilisés comme entrées dans l'éditeur de liens doivent être constitués de code MSIL pur pouvant être produit par le compilateur Visual C\+\+ à l'aide de **\/clr:safe**.  D'autres compilateurs Visual Studio produisent des modules MSIL purs par défaut.  
  
 Pour plus d'informations sur l'appel de l'éditeur de liens à partir de la ligne de commande, consultez [Syntaxe de la ligne de commande de l'Éditeur de liens](../../build/reference/linker-command-line-syntax.md) et [Définition du chemin d'accès et des variables d'environnement pour la génération à partir de la ligne de commande](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
 Passer un fichier .netmodule ou .dll à l'éditeur de liens qui a été compilé par le compilateur Visual C\+\+ avec **\/clr** ou **\/clr:pure** peut provoquer une erreur de l'éditeur de liens.  Pour plus d'informations, consultez [Choix du format des fichiers d'entrée .netmodule](../../build/reference/choosing-the-format-of-netmodule-input-files.md).  
  
 L'éditeur de liens accepte les fichiers .obj natifs ainsi que les fichiers .obj MSIL compilés avec **\/clr**, **\/clr:pure**ou **\/clr:safe**.  Lors du passage de fichiers .obj mixtes dans la même version, la vérifiabilité du fichier de sortie résultant équivaut par défaut au niveau le plus bas de vérifiabilité des modules d'entrée.  Par exemple, si vous passez un fichier .obj sécurisé \(mode safe\) et pur \(mode pure\) à l'éditeur de liens, vous obtiendrez un fichier de sortie pur.  [\/CLRIMAGETYPE \(Spécifier le type d'une image CLR\)](../../build/reference/clrimagetype-specify-type-of-clr-image.md) vous permet de spécifier un niveau de vérifiabilité inférieur, si nécessaire.  
  
 Si vous disposez actuellement d'une application composée de plusieurs assemblys et que vous souhaitez l'inclure dans un seul assembly, vous devez recompiler les assemblys, puis lier les fichiers .obj ou .netmodules pour produire un assembly unique.  
  
 Vous devez spécifier un point d'entrée à l'aide de [\/ENTRY \(Symbole de point d'entrée\)](../../build/reference/entry-entry-point-symbol.md) lors de la création d'une image exécutable.  
  
 Lorsque la liaison à un fichier .obj MSIL ou .netmodule, utilisez [\/LTCG \(Génération de code durant l'édition de liens\)](../../build/reference/ltcg-link-time-code-generation.md), sinon, lorsque l'éditeur de liens rencontre le .obj MSIL ou le .netmodule, il redémarrera le lien avec \/LTCG.  
  
 Les fichiers MSIL .obj ou .netmodule peuvent également être passés à cl.exe.  
  
 Les fichiers d'entrée .obj MSIL ou .netmodule ne peuvent pas avoir de ressources incorporées.  Une ressource est incorporée dans un fichier de sortie \(module ou assembly\) avec l'option de l'éditeur de liens [\/ASSEMBLYRESOURCE \(Incorporer une ressource managée\)](../../build/reference/assemblyresource-embed-a-managed-resource.md) ou avec l'option du compilateur **\/resource** dans d'autres compilateurs Visual Studio.  
  
 Lors de l'exécution de la liaison MSIL, si vous ne spécifiez pas également [\/LTCG \(Génération de code durant l'édition de liens\)](../../build/reference/ltcg-link-time-code-generation.md), un message d'information s'affiche pour signaler que la liaison redémarre.  Ce message peut être ignoré, mais pour améliorer les performances de l'éditeur de liens avec la liaison MSIL, spécifiez explicitement **\/LTCG**.  
  
## Exemple  
 Dans le code C\+\+, le bloc catch d'une clause try correspondante est appelé pour une exception autre que System.  Toutefois, le CLR encapsule par défaut les exceptions autres que System avec <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.  Lorsqu'un assembly est créé à partir de modules Visual C\+\+ et autres et que vous souhaitez appeler un bloc catch dans le code C\+\+ à partir de sa clause try correspondante lorsque le bloc try lève une exception autre que System, vous devez ajouter  
  
 l'attribut \[assembly:System::Runtime::CompilerServices::RuntimeCompatibility \(WrapNonExceptionThrows\=false\)\] au code source pour les modules autres que C\+\+.  
  
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
  
## Exemple  
 En modifiant la valeur Boolean de l'attribut WrapNonExceptionThrows, le code Visual C\+\+ ne peut pas intercepter une exception autre que System.  
  
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
  
  **exception autre que système attrapée dans le fichier de code source en C\+\+**   
## Voir aussi  
 [Fichiers d'entrée LINK](../../build/reference/link-input-files.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)