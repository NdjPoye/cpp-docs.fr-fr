---
title: Importation et exportation de DLL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- dllimport attribute [C++], storage-class attribute
- DLL exports [C++]
- declaring functions, with dllexport and dllimport
- extended storage-class attributes
- dllexport attribute [C++], storage-class attribute
ms.assetid: 08d164b9-770a-4e14-afeb-c6f21d9e33e4
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 96f683c796de60daabfc2da43f8e6a0a4849a535
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="dll-import-and-export-functions"></a>Fonctions d'importation et d'exportation de DLL
**Section spécifique à Microsoft**  
  
 Les informations les plus complètes et récentes à ce sujet se trouvent dans la rubrique [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
 Les modificateurs de classe de stockage **dllimport** et `dllexport` sont des extensions spécifiques à Microsoft pour le langage C. Ces modificateurs définissent explicitement l'interface de la DLL à son client (le fichier exécutable ou une autre DLL). La déclaration de fonctions comme `dllexport` élimine le besoin d'utiliser un fichier de définition de module (.DEF). Vous pouvez également utiliser les modificateurs **dllimport** et `dllexport` avec des données et des objets.  
  
 Les modificateurs de classe de stockage **dllimport** et `dllexport` doivent être utilisés avec le mot clé de syntaxe à attributs étendus, `__declspec`, comme indiqué dans l'exemple suivant :  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport void func();  
DllExport int i = 10;  
DllExport int j;  
DllExport int n;  
```  
  
 Pour obtenir des informations spécifiques sur la syntaxe des modificateurs étendus de classe de stockage, consultez [Attributs étendus de classe de stockage](../c-language/c-extended-storage-class-attributes.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Définitions de fonction C](../c-language/c-function-definitions.md)
