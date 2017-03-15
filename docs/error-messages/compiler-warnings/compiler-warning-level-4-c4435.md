---
title: "Avertissement du compilateur (niveau&#160;4) C4435 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# Avertissement du compilateur (niveau&#160;4) C4435
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe1' : la disposition des objets sous \/vd2 sera modifiée en raison de la base virtuelle 'classe2'  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Dans l'option de compilation par défaut de \/vd1, la classe dérivée n'a pas de champ de `vtordisp` pour la base virtuelle indiquée.  Si \/vd2 ou `#pragma vtordisp(2)` est activé, un champ de `vtordisp` sera présent, modifiant la disposition de l'objet.  Cela peut provoquer des problèmes de compatibilité binaire si les modules en interaction sont compilés avec des paramètres de `vtordisp` différents.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4435.  
  
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
  
## Voir aussi  
 [vtordisp](../../preprocessor/vtordisp.md)   
 [\/vd \(Désactiver les déplacements de construction\)](../../build/reference/vd-disable-construction-displacements.md)