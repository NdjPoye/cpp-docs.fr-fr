---
title: "R&#233;sum&#233; de la dur&#233;e de vie et de la visibilit&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "durée de vie, et visibilité"
  - "visibilité, identificateurs"
ms.assetid: ea05a253-7658-482c-9a6b-abd71169c42d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;sum&#233; de la dur&#233;e de vie et de la visibilit&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant récapitule les caractéristiques de durée de vie et de visibilité pour la plupart des identificateurs.  Les trois premières colonnes indiquent les attributs qui définissent la durée de vie et la visibilité.  Un identificateur avec les attributs indiqués par les trois premières colonnes a la durée de vie et la visibilité affichées dans les quatrième et cinquième colonnes.  Toutefois, le tableau ne traite pas tous les cas possibles.  Pour plus d'informations, consultez [Classes de stockage](../c-language/c-storage-classes.md).  
  
### Résumé de la durée de vie et de la visibilité  
  
|Attributs :<br /><br /> Niveau|Élément|Classe de stockage<br /><br /> Spécificateur|Résultat :<br /><br /> Durée de vie|Visibilité|  
|----------------------------|-------------|------------------------------------------|---------------------------------|----------------|  
|Portée du fichier|Définition de variable|**static**|Global|Reste du fichier source dans lequel elle se produit|  
||Déclaration de variable|`extern`|Global|Reste du fichier source dans lequel elle se produit|  
||Définition ou prototype de fonction|**static**|Global|Fichier source unique|  
||Prototype de fonction|`extern`|Global|Reste du fichier source|  
|Portée de bloc|Déclaration de variable|`extern`|Global|Bloc|  
||Définition de variable|**static**|Global|Bloc|  
||Définition de variable|**auto** ou **register**|Local|Bloc|  
  
## Exemple  
  
### Description  
 L'exemple suivant illustre les blocs, l'imbrication et la visibilité des variables :  
  
### Code  
  
```  
// Lifetime_and_Visibility.c  
  
#include <stdio.h>  
  
int i = 1;  // i defined at external level  
  
int main()  // main function defined at external level  
{  
    printf_s( "%d\n", i ); // Prints 1 (value of external level i)  
    {                                 // Begin first nested block  
        int i = 2, j = 3;          // i and j defined at internal level  
        printf_s( "%d %d\n", i, j );  // Prints 2, 3  
        {                             // Begin second nested block  
            int i = 0;                // i is redefined  
            printf_s( "%d %d\n", i, j ); // Prints 0, 3  
        }                             // End of second nested block  
        printf_s( "%d\n", i );        // Prints 2 (outer definition  
                                      //  restored)  
    }                                 // End of first nested block  
    printf_s( "%d\n", i );            // Prints 1 (external level  
                                      // definition restored)  
    return 0;  
}   
```  
  
### Commentaires  
 Dans cet exemple, il existe quatre niveaux de visibilité : le niveau externe et trois niveaux de bloc.  Les valeurs sont imprimées à l'écran comme indiqué dans les commentaires suivant chaque instruction.  
  
## Voir aussi  
 [Durée de vie, portée, visibilité et liaison](../c-language/lifetime-scope-visibility-and-linkage.md)