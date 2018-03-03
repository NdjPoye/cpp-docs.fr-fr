---
title: Compilateur avertissement (niveau 4) C4435 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7136cfb61a7452b7e835030216d08f064874df8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4435"></a>Avertissement du compilateur (niveau 4) C4435
'classe1' : la disposition des objets sous /vd2 sera modifiée en raison de la base virtuelle 'classe2'  
  
 Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.  
  
 Sous la valeur par défaut l’option de/vd1 de compilation, la classe dérivée n’a pas un `vtordisp` pour la base virtuelle indiquée.  Si/vd2 ou `#pragma vtordisp(2)` est activée, un `vtordisp` champ est présent, la modification de la disposition de l’objet.  Cela peut entraîner des problèmes de compatibilité binaire si l’interaction des modules compilés avec différents `vtordisp` paramètres.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4435.  
  
```cpp  
// C4435.cpp  
// compile with: /c /W4  
#pragma warning(default : 4435)  
class A  
{  
public:  
    virtual ~A() {}  
};  
  
class B : public virtual A  // C4435  
{};  
```  
  
## <a name="see-also"></a>Voir aussi  
 [vtordisp](../../preprocessor/vtordisp.md)   
 [/vd (désactiver les déplacements de Construction)](../../build/reference/vd-disable-construction-displacements.md)