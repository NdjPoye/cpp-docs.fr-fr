---
title: Compilateur avertissement (niveau 1) C4251 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4251
dev_langs:
- C++
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: b75c3e6c93c0963a692b210b158339ea5e9eacac
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4251"></a>Avertissement du compilateur (niveau 1) C4251
'identificateur' : classe 'type' doit avoir une interface dll pour être utilisé par les clients de la classe 'type2'  
  
 Pour minimiser le risque d’altération des données lors de l’exportation d’une classe avec [__declspec (dllexport)](../../cpp/dllexport-dllimport.md), vérifiez que :  
  
-   Toutes vos données statiques est l’accès via les fonctions exportées à partir de la DLL.  
  
-   Aucune méthode inline de votre classe ne permettre modifier les données statiques.  
  
-   Aucune méthode inline de votre classe n’utilise des fonctions CRT ou d’autres fonctions de bibliothèque utilisent des données statiques (voir [potentielles erreurs passant CRT Objects Across DLL Boundaries](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) pour plus d’informations).  
  
-   Aucune méthode de votre classe (indépendamment du incorporation) peuvent utiliser des types où l’instanciation dans le fichier EXE et DLL présentent les différences de données statiques.  
  
 Vous pouvez éviter d’exporter des classes en définissant une DLL qui définit une classe avec des fonctions virtuelles et les fonctions que vous pouvez appeler pour instancier et de supprimer des objets du type.  Vous pouvez ensuite simplement appeler des fonctions virtuelles sur le type.  
  
 Pour plus d’informations sur l’exportation de modèles, consultez [http://support.microsoft.com/default.aspx?scid=KB; EN-US ;&16895;8](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 C4251 peut être ignorée si vous dérivez d’un type dans la bibliothèque C++ Standard, compilez une version debug (**/MTd**) et si le message d’erreur du compilateur fait référence à _Container_base.  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```
