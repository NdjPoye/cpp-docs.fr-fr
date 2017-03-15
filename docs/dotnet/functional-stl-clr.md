---
title: "functional (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/functional>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <cliext/functional> (STL/CLR)"
  - "en-tête <functional> (STL/CLR)"
  - "fonctions fonctionnelles (STL/CLR)"
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# functional (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Incluez l'en\-tête `<cliext/functional>` de STL\/CLR pour définir plusieurs classes du modèle et les modèles associés de délégués et de fonctions.  
  
## Syntaxe  
  
```  
#include <functional>  
```  
  
## Déclarations  
  
|Délégué|Description|  
|-------------|-----------------|  
|[binary\_delegate](../dotnet/binary-delegate-stl-clr.md)|Délégué de deux arguments.|  
|[binary\_delegate\_noreturn](../dotnet/binary-delegate-noreturn-stl-clr.md)|Délégué de deux arguments retournant `void`.|  
|[unary\_delegate](../dotnet/unary-delegate-stl-clr.md)|Délégué d'un argument.|  
|[unary\_delegate\_noreturn](../dotnet/unary-delegate-noreturn-stl-clr.md)|Délégué d'un argument retournant `void`.|  
  
|Classe|Description|  
|------------|-----------------|  
|[binary\_negate](../dotnet/binary-negate-stl-clr.md)|Functor pour inverser un functor de deux arguments.|  
|[binder1st](../dotnet/binder1st-stl-clr.md)|Functor pour lier le premier argument à un functor de deux arguments.|  
|[binder2nd](../dotnet/binder2nd-stl-clr.md)|Functor pour lier le deuxième argument à un functor de deux arguments.|  
|[divides](../dotnet/divides-stl-clr.md)|Functor de division.|  
|[equal\_to](../dotnet/equal-to-stl-clr.md)|Functor de comparaison égale.|  
|[greater](../dotnet/greater-stl-clr.md)|Functor de comparaison de supériorité.|  
|[greater\_equal](../dotnet/greater-equal-stl-clr.md)|Functor de comparaison supérieur ou égal.|  
|[less](../dotnet/less-stl-clr.md)|Functor de comparaison d'infériorité.|  
|[less\_equal](../dotnet/less-equal-stl-clr.md)|Functor de comparaison inférieur ou égal.|  
|[logical\_and](../dotnet/logical-and-stl-clr.md)|Functor de ET logique.|  
|[logical\_not](../dotnet/logical-not-stl-clr.md)|Functor de NON logique.|  
|[logical\_or](../dotnet/logical-or-stl-clr.md)|Functor de OU logique.|  
|[minus](../dotnet/minus-stl-clr.md)|Functor de soustraction.|  
|[modulo](../dotnet/modulus-stl-clr.md)|Functor modulo.|  
|[multiplies](../dotnet/multiplies-stl-clr.md)|Functor de multiplication.|  
|[negate](../dotnet/negate-stl-clr.md)|Functor pour retourner l'argument après une négation.|  
|[not\_equal\_to](../dotnet/not-equal-to-stl-clr.md)|Functor de comparaison de différence.|  
|[plus](../dotnet/plus-stl-clr.md)|Functor d'addition.|  
|[unary\_negate](../dotnet/unary-negate-stl-clr.md)|Functor pour inverser un functor à un argument.|  
  
|Fonction|Description|  
|--------------|-----------------|  
|[bind1st](../dotnet/bind1st-stl-clr.md)|Génère un binder1st pour un argument et un functor.|  
|[bind2nd](../dotnet/bind2nd-stl-clr.md)|Génère un binder2nd pour un argument et un functor.|  
|[not1](../dotnet/not1-stl-clr.md)|Génère un unary\_negate pour un functor.|  
|[not1](../dotnet/not1-stl-clr.md)|Génère un binary\_negate pour un functor.|  
  
## Configuration requise  
 **En\-tête :** \<cliext\/functional\>  
  
 **Espace de noms :** cliext  
  
## Voir aussi  
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)