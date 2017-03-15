---
title: "Importation dans une application &#224; l&#39;aide de&#160;__declspec(dllimport) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__declspec"
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport) (mot clé C++)"
  - "importer des DLL (C++), __declspec(dllimport)"
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Importation dans une application &#224; l&#39;aide de&#160;__declspec(dllimport)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un programme qui utilise des symboles publics définis par une DLL est réputé les importer.  Lorsque vous créez des fichiers d'en\-tête pour des applications qui utilisent vos DLL pour la génération, utilisez **\_\_declspec\(dllimport\)** sur les déclarations des symboles publics.  Le mot clé **\_\_declspec\(dllimport\)** fonctionne que vous effectuiez l'exportation avec des fichiers .def ou avec le mot clé **\_\_declspec\(dllexport\)**.  
  
 Pour rendre le code plus lisible, définissez une macro pour **\_\_declspec\(dllimport\)** puis utilisez cette macro pour déclarer chaque symbole importé :  
  
```  
#define DllImport   __declspec( dllimport )  
  
DllImport int  j;  
DllImport void func();  
```  
  
 L'utilisation de **\_\_declspec\(dllimport\)** est facultative dans les déclarations de fonctions, mais le compilateur produit un code plus performant quand vous utilisez ce mot clé.  Cependant, vous devez utiliser **\_\_declspec\(dllimport\)** afin de permettre à l'exécutable importateur d'accéder aux objets et aux symboles de données publics de la DLL.  Notez que les utilisateurs de votre DLL doivent quand même établir une liaison avec une bibliothèque d'importation.  
  
 Vous pouvez utiliser le même fichier d'en\-tête à la fois pour la DLL et l'application cliente.  Pour ce faire, utilisez un symbole de préprocesseur spécial qui indique si vous générez la DLL ou l'application cliente.  Par exemple :  
  
```  
#ifdef _EXPORTING  
   #define CLASS_DECLSPEC    __declspec(dllexport)  
#else  
   #define CLASS_DECLSPEC    __declspec(dllimport)  
#endif  
  
class CLASS_DECLSPEC CExampleA : public CObject  
{ ... class definition ... };  
```  
  
## Que voulez\-vous faire ?  
  
-   [Initialiser une DLL](../build/initializing-a-dll.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Importation et exportation de fonctions inline](../build/importing-and-exporting-inline-functions.md)  
  
-   [Importations mutuelles](../build/mutual-imports.md)  
  
## Voir aussi  
 [Importation dans une application](../build/importing-into-an-application.md)