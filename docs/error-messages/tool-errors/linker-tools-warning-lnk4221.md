---
title: "Avertissement des outils &#201;diteur de liens LNK4221 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4221"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4221"
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Avertissement des outils &#201;diteur de liens LNK4221
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce fichier objet ne définit pas de symboles publics jusqu'ici non définis. Par conséquent, il ne sera utilisé par aucune opération de lien utilisant cette bibliothèque  
  
 Prenons les deux extraits de code suivants.  
  
```  
// a.cpp  
#include <atlbase.h>  
```  
  
```  
// b.cpp  
#include <atlbase.h>  
int function()  
{  
   return 0;  
}  
  
```  
  
 Pour compiler les fichiers et créer deux fichiers objets, exécutez **cl \/c a.cpp b.cpp** à une invite de commandes.  Si vous liez les fichiers objets en exécutant **link \/lib \/out:test.lib a.obj b.obj**, vous recevrez l'avertissement LNK4221.  Si vous liez les objets en exécutant **link \/lib \/out:test.lib b.obj a.obj**, vous ne recevrez pas d'avertissement.  
  
 Aucun avertissement n'est émis dans le deuxième scénario, car l'éditeur de liens observe une approche de type dernier entré, premier sorti \(LIFO\).  Dans le premier scénario, b.obj est traité avant a.obj, et a.obj n'a aucun nouveau symbole à ajouter.  En indiquant à l'éditeur de liens de traiter d'abord a.obj, vous pouvez éviter l'avertissement.  
  
 Une cause courante de cette erreur est la spécification par deux fichiers sources de l'option [\/Yc \(Créer un fichier d'en\-tête précompilé\)](../../build/reference/yc-create-precompiled-header-file.md) avec le même nom de fichier d'en\-tête spécifié dans le champ **En\-tête précompilé**.  Une cause courante de ce problème est liée à stdafx.h dans la mesure où, par défaut, stdafx.cpp inclut stdafx.h et n'ajoute pas de nouveaux symboles.  Si un autre fichier source inclut stdafx.h avec **\/Yc** et que le fichier .obj associé est traité avant stdafx.obj, l'éditeur de liens lèvera l'avertissement LNK4221.  
  
 L'une des méthodes permettant de résoudre ce problème consiste à s'assurer que chaque en\-tête précompilé est inclut avec **\/Yc** dans un seul fichier source.  Tous les autres fichiers sources doivent utiliser des en\-têtes précompilés.  Pour plus d'informations sur la modification de ce paramètre, consultez [\/Yu \(Utiliser un fichier d'en\-tête précompilé\)](../../build/reference/yu-use-precompiled-header-file.md).