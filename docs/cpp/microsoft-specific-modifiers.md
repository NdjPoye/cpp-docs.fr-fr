---
title: "Modificateurs sp&#233;cifiques Microsoft | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Modificateurs sp&#233;cifiques Microsoft
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette section décrit les extensions C\+\+ spécifiques à Microsoft dans les domaines suivants :  
  
-   [Adressage avec base](../cpp/based-addressing.md), pratique consistant à utiliser un pointeur comme base par rapport à laquelle d'autres pointeurs peuvent être décalés  
  
-   [Conventions d'appel de fonction](../cpp/calling-conventions.md)  
  
-   Attributs de classe de stockage étendus, déclarés avec le mot clé [\_\_declspec](../cpp/declspec.md)  
  
-   Mot clé [\_\_w64](../cpp/w64.md)  
  
 Un grand nombre des mots clés spécifiques à Microsoft peuvent être utilisés pour modifier des déclarateurs afin de former des types dérivés.  Pour plus d'informations sur les déclarateurs, consultez [Déclarateurs](http://msdn.microsoft.com/fr-fr/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).  
  
### Mots clés spécifiques à Microsoft  
  
|Mot clé|Signification|Utilisé pour former des types dérivés ?|  
|-------------|-------------------|---------------------------------------------|  
|[\_\_based](../cpp/based-grammar.md)|Le nom qui suit déclare un décalage de 32 bits par rapport à la base 32 bits contenue dans la déclaration.|Oui|  
|[\_\_cdecl](../cpp/cdecl.md)|Le nom qui suit utilise les conventions de nommage et d'appel du langage C.|Oui|  
|[\_\_declspec](../cpp/declspec.md)|Le nom qui suit spécifie un attribut de classe de stockage spécifique à Microsoft.|Non|  
|[\_\_fastcall](../cpp/fastcall.md)|Le nom qui suit déclare une fonction qui utilise des registres, lorsqu'ils sont disponibles, à la place de la pile, pour transmettre des arguments.|Oui|  
|[\_\_restrict](../cpp/extension-restrict.md)|Similaire à \_\_declspec\([restrict](../cpp/restrict.md)\) mais à utiliser sur les variables.|Non|  
|[\_\_stdcall](../cpp/stdcall.md)|Le nom qui suit spécifie une fonction qui respecte la convention d'appel standard.|Oui|  
|[\_\_w64](../cpp/w64.md)|Marque un type de données comme étant plus grand sur un compilateur 64 bits.|Non|  
|[\_\_unaligned](../cpp/unaligned.md)|Spécifie qu'un pointeur désignant un type ou d'autres données n'est pas aligné.|Non|  
|[\_\_vectorcall](../cpp/vectorcall.md)|Le nom qui suit déclare une fonction qui utilise des registres, y compris les registres SSE lorsqu'ils sont disponibles, à la place de la pile, pour transmettre des arguments.|Oui|  
  
## Voir aussi  
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)