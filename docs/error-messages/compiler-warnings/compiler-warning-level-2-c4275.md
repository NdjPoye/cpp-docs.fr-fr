---
title: "Une erreur C4275 (niveau 2) d’avertissement de compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4275
dev_langs:
- C++
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
caps.latest.revision: 14
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 873a96d4595b75ff6b9567500723c32d7ba5bd2b
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4275"></a>Avertissement du compilateur (niveau 2) C4275
non – une interface DLL LocalizedText 'identificateur' utilisée comme base pour une interface DLL classkey 'identificateur'  
  
 Une classe exportée a été dérivée d’une classe qui n’a pas été exportée.  
  
 Pour minimiser le risque d’altération des données lors de l’exportation d’une classe avec [__declspec (dllexport)](../../cpp/dllexport-dllimport.md), vérifiez que :  
  
-   Toutes vos données statiques est accessible via les fonctions exportées à partir de la DLL.  
  
-   Aucune méthode inline de votre classe ne permettre modifier les données statiques.  
  
-   Aucune méthode inline de votre classe n’utilise des fonctions CRT ou d’autres fonctions de bibliothèque utilisent des données statiques.  
  
-   Aucune fonctions inline n’utilisent des fonctions CRT, ou autres fonctions de la bibliothèque, où, par exemple, vous accéder aux données statiques.  
  
-   Aucune méthode de votre classe (indépendamment du incorporation) peuvent utiliser des types où l’instanciation dans le fichier EXE et DLL présentent les différences de données statiques.  
  
 Vous pouvez éviter d’exporter des classes en définissant une DLL qui définit une classe avec des fonctions virtuelles et les fonctions que vous pouvez appeler pour instancier et de supprimer des objets du type.  Vous pouvez ensuite simplement appeler des fonctions virtuelles sur le type.  
  
 Pour plus d’informations sur l’exportation de modèles, consultez [http://support.microsoft.com/default.aspx?scid=KB; EN-US ;&16895;8](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 Une erreur C4275 peut être ignorée dans Visual C++ si vous dérivez d’un type dans la bibliothèque C++ Standard, compilez une version debug (**/MTd**) et si le message d’erreur du compilateur fait référence à _Container_base.  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```
