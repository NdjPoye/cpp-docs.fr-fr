---
title: Erreur du compilateur C2813 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: fc5f5437751abf6bcb11299e8484a199275db970
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2813"></a>Erreur du compilateur C2813
\#importation n’est pas prise en charge avec /MP  
  
 L’erreur C2813 est émise si dans une commande du compilateur que vous spécifiez la **/MP** option du compilateur et deux ou plusieurs fichiers à la compilation et un ou plusieurs des fichiers contient la[#import](../../preprocessor/hash-import-directive-cpp.md) directive de préprocesseur. Le [#import](../../preprocessor/hash-import-directive-cpp.md) directive génère des classes C++ à partir des types dans la bibliothèque de types spécifiée, puis écrit ces classes dans deux fichiers d’en-tête. Le [#import](../../preprocessor/hash-import-directive-cpp.md) directive n’est pas prise en charge, car si plusieurs unités de compilation importent la même bibliothèque de types, les unités en conflit lorsqu’ils tentent d’écrire des fichiers d’en-tête en même temps.  
  
 Cette erreur du compilateur et la **/MP** option du compilateur sont une nouveauté de [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)].  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2813. La ligne de commande située dans le commentaire « compiler avec : » indique au compilateur d’utiliser les options **/MP** et **/c** pour compiler plusieurs fichiers. Au moins un des fichiers contient la [#import](../../preprocessor/hash-import-directive-cpp.md) directive. Nous utilisons le même fichier à deux reprises pour tester cet exemple.  
  
```  
// C2813.cpp  
// compile with: /MP /c C2813.cpp C2813.cpp  
#import "C:\windows\system32\stdole2.tlb"   // C2813  
int main()   
{  
}  
```
