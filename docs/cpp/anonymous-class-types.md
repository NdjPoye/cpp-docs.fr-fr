---
title: "Types de classe anonymes | Microsoft Docs"
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
helpviewer_keywords: 
  - "types de classe anonyme"
  - "types de classes, anonymes"
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Types de classe anonymes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes peuvent être anonymes \(autrement dit, elles peuvent être déclarées sans *identifier*\).  Cela est utile lorsque vous remplacez un nom de classe par un nom de `typedef`, comme dans l'exemple suivant :  
  
```  
typedef struct  
{  
    unsigned x;  
    unsigned y;  
} POINT;  
```  
  
> [!NOTE]
>  L'utilisation de classes anonymes indiquée dans l'exemple précédent est utile pour conserver la compatibilité avec un code C existant.  Dans du code C, l'utilisation de `typedef` conjointement aux structures anonymes est généralisée.  
  
 Les classes anonymes sont également utiles lorsque vous souhaitez qu'une référence à un membre de classe apparaisse comme si elle n'était pas été contenue dans une classe distincte, comme dans l'exemple suivant :  
  
```  
struct PTValue  
{  
    POINT ptLoc;  
    union  
    {  
        int  iValue;  
        long lValue;  
    };  
};  
  
PTValue ptv;  
```  
  
 Dans le code précédent, `iValue` est accessible via l'opérateur de sélection de membres d'objet \(**.**\) comme suit :  
  
```  
int i = ptv.iValue;  
```  
  
 Les classes anonymes sont soumises à certaines restrictions.  \(Pour plus d'informations sur les unions anonymes, consultez [Unions](../cpp/unions.md).\) Classes anonymes :  
  
-   Ne peut pas avoir de constructeur ou de destructeur.  
  
-   Ne peut pas être passé en tant qu'argument aux fonctions \(à moins que la vérification de type soit invalidée en utilisant des points de suspension\).  
  
-   Ne peut pas être retourné comme valeurs de retour à partir des fonctions.  
  
## Structs anonymes  
  
### Section spécifique à Microsoft  
 Une extension Microsoft C vous permet de déclarer une variable de structure dans une autre structure sans lui donner un nom.  Ces structures imbriquées sont appelées des structures anonymes.  C\+\+ n'autorise pas les structures anonymes.  
  
 Vous pouvez accéder aux membres d'une structure anonyme comme s'ils étaient des membres de la structure conteneur.  
  
```  
// anonymous_structures.c  
#include <stdio.h>  
  
struct phone  
{  
    int  areacode;  
    long number;  
};  
  
struct person  
{  
    char   name[30];  
    char   gender;  
    int    age;  
    int    weight;  
    struct phone;    // Anonymous structure; no name needed  
} Jim;  
  
int main()  
{  
    Jim.number = 1234567;  
    printf_s("%d\n", Jim.number);     
}  
//Output: 1234567  
```  
  
### FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [\(NOTINBUILD\) Defining Class Types](http://msdn.microsoft.com/fr-fr/e8c65425-0f3a-4dca-afc2-418c3b1e57da)