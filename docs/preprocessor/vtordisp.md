---
title: "vtordisp | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.vtordisp"
  - "vtordisp_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "pragmas, vtordisp"
  - "vtordisp (pragma)"
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vtordisp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Contrôle l'ajout du membre de déplacement de construction\/destruction vtordisp masqué.  
  
## Syntaxe  
  
```cpp  
#pragma vtordisp([push,] n)  
#pragma vtordisp(pop)  
#pragma vtordisp()  
#pragma vtordisp([push,] {on | off})  
```  
  
#### Paramètres  
 `push`  
 Pousse le paramètre vtordisp actuel sur la pile interne du compilateur et affecte la valeur `n` au nouveau paramètre vtordisp.  Si la valeur `n` n'est pas spécifiée, le paramètre vtordisp actuel n'est pas modifié.  
  
 `pop`  
 Supprime l'enregistrement supérieur de la pile interne du compilateur et rétablit la valeur supprimée du paramètre vtordisp.  
  
 `n`  
 Spécifie la nouvelle valeur du paramètre vtordisp.  Les valeurs possibles sont 0, 1 et 2, qui correspondent aux options \/vd0, \/vd1 et \/vd2 du compilateur.  Pour plus d'informations, consultez [\/vd \(Désactiver les déplacements de construction\)](../build/reference/vd-disable-construction-displacements.md).  
  
 `on`  
 Équivalent à `#pragma vtordisp(1)`.  
  
 `off`  
 Équivalent à `#pragma vtordisp(0)`.  
  
## Notes  
 Le pragma `vtordisp` peut s'appliquer uniquement à du code qui utilise des bases virtuelles.  Si une classe dérivée remplace une fonction virtuelle qu'elle hérite d'une classe de base virtuelle et si un constructeur ou un destructeur pour la classe dérivée appelle cette fonction à l'aide d'un pointeur vers la classe de base virtuelle, le compilateur peut introduire des champs `vtordisp` masqués supplémentaires dans les classes dotées de bases virtuelles.  
  
 Le pragma `vtordisp` affecte la disposition des classes qui le suivent.  Les options \/vd0, \/vd1 et \/vd2 spécifient le même comportement pour les modules complets.  La spécification de `0` ou `off` supprime les membres `vtordisp` masqués.  Désactivez `vtordisp` seulement s'il n'est pas possible que les constructeurs et les destructeurs de la classe appellent des fonctions virtuelles sur l'objet vers lequel pointe le pointeur `this`.  
  
 La spécification de `1` ou `on` \(valeur par défaut\) active les membres `vtordisp` masqués là où ils sont nécessaires.  
  
 La spécification de `2` active les membres `vtordisp` masqués pour toutes les bases virtuelles avec des fonctions virtuelles. `vtordisp(2)` peut être nécessaire pour garantir des performances correctes de `dynamic_cast` sur un objet partiellement construit.  Pour plus d'informations, consultez [Avertissement du compilateur \(niveau 1\) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).  
  
 `#pragma vtordisp()`, sans argument, rétablit la valeur initiale du paramètre vtordisp.  
  
```  
#pragma vtordisp(push, 2)  
class GetReal : virtual public VBase { ... };  
#pragma vtordisp(pop)  
```  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)