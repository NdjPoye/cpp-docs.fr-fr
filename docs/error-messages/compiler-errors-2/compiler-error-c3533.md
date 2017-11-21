---
title: Erreur du compilateur C3533 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3533
dev_langs: C++
helpviewer_keywords: C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b519a08080edb8dda37760bd826224657365afae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3533"></a>Erreur du compilateur C3533
'type' : un paramètre ne peut pas avoir un type contenant 'auto'  
  
 Une méthode ou paramètre de modèle ne peut pas être déclaré avec le `auto` mot clé si la valeur par défaut [/Zc : auto](../../build/reference/zc-auto-deduce-variable-type.md) option du compilateur est en vigueur.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  Supprimer le `auto` (mot clé) à partir de la déclaration de paramètre.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant donne C3535 parce qu’il déclare un paramètre de fonction avec la `auto` (mot clé) et il est compilé avec **/Zc : auto**.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant donne C3535 parce qu’il déclare un paramètre de modèle avec le `auto` (mot clé) et il est compilé avec **/Zc : auto**.  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## <a name="see-also"></a>Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)   
 [/ Zc : auto (déduire le Type de Variable)](../../build/reference/zc-auto-deduce-variable-type.md)