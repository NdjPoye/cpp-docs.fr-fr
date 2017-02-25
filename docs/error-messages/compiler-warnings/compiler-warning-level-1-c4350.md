---
title: "Avertissement du compilateur (niveau 1) C4350 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4350"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4350"
ms.assetid: 4cc8ed67-64c4-4da5-a7a5-a639232baa23
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4350
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

changement de comportement : 'membre1' appelé à la place de 'membre2'  
  
 Une rvalue ne peut pas être liée à une référence non const.  Dans les versions antérieures de Visual C\+\+, il était possible de lier une rvalue à une référence non const dans une initialisation directe.  Ce code génère désormais un avertissement.  
  
 À des fins de compatibilité descendante, il est encore possible de lier des rvalues à des références non const, mais les conversions standard sont conseillées dans la mesure du possible.  
  
 Cet avertissement représente une modification du comportement par rapport au compilateur de Visual C\+\+ .NET 2002.  S'il est activé, cet avertissement peut être généré pour un code correct.  Par exemple, il peut s'afficher lors de l'utilisation du modèle de classe **std::auto\_ptr**.  
  
 Si vous rencontrez cet avertissement, examinez votre code pour déterminer s'il dépend de la liaison de rvalue à des références non const.  Le problème peut être résolu en ajoutant une constante à la référence ou en fournissant une surcharge de référence const supplémentaire.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 L'exemple suivant génère l'erreur C4350 :  
  
```  
// C4350.cpp  
// compile with: /W1  
#pragma warning (default : 4350)  
class A {};  
  
class B  
{  
public:  
   B(B&){}  
   // try the following instead  
   // B(const B&){}  
  
   B(A){}  
   operator A(){ return A();}  
};  
  
B source() { return A(); }  
  
int main()  
{  
   B ap(source());   // C4350  
}  
```