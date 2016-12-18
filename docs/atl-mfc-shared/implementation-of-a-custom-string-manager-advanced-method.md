---
title: "Implementation of a Custom String Manager (Advanced Method) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlStringMgr class, using"
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementation of a Custom String Manager (Advanced Method)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans les configurations spécialisées, vous pouvez souhaiter implémenter un gestionnaire de chaînes personnalisé qui fait plus que la modification que le tas est utilisé pour allouer de la mémoire.  Dans cette situation, vous devez manuellement implémenter l'interface d' [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) comme votre gestionnaire de chaînes personnalisé.  
  
 Pour ce faire, il est important d'abord incluent comment les utilisations de [CStringT](../atl-mfc-shared/reference/cstringt-class.md) interface qui gérer ses données de chaîne.  Chaque instance d' `CStringT` un pointeur vers une structure de [CStringData](../atl-mfc-shared/reference/cstringdata-class.md) .  Cette structure de longueur variable contient des informations importantes concernant la chaîne \(telle que la longueur\), ainsi que des données réelles caractères de la chaîne.  Chaque gestionnaire de chaînes personnalisé est chargé d'allouer et à libérer ces structures sur demande d' `CStringT`.  
  
 La structure d' `CStringData` comporte quatre champs :  
  
-   [pStringMgr](../Topic/CStringData::pStringMgr.md) points de ce champ à l'interface d' `IAtlStringMgr` utilisée pour gérer ces données de chaîne.  Lorsque les besoins d' `CStringT` de réaffecter ou libérer la mémoire tampon de chaîne il appelle le réaffecter ou libère des méthodes de cette interface, en passant la structure d' `CStringData` comme paramètre.  En allouant une structure d' `CStringData` dans votre gestionnaire de chaînes, vous devez définir ce champ pour indiquer le gestionnaire de chaînes personnalisé.  
  
-   [nDataLength](../Topic/CStringData::nDataLength.md) ce champ contient la longueur logique actuelle de la chaîne stockée dans la mémoire tampon à l'exclusion de null de fin.  `CStringT` met à jour le champ lorsque la longueur de la chaîne est modifiée.  En allouant une structure d' `CStringData` , votre gestionnaire de chaînes doit définir ce champ à zéro.  En réaffectant une structure d' `CStringData` , votre gestionnaire de chaînes personnalisé doit quitter ce champ inchangé.  
  
-   [nAllocLength](../Topic/CStringData::nAllocLength.md) ce champ contient le nombre maximal de caractères \(à l'exclusion de null de fin\) qui peuvent être stockés dans cette mémoire tampon de chaîne sans le réaffecter.  Chaque fois que les besoins d' `CStringT` d'augmenter la longueur logique de la chaîne, il vérifie d'abord ce champ pour vous assurer qu'il y a suffisamment d'espace dans la mémoire tampon.  Si la vérification échoue, les appels d' `CStringT` dans votre gestionnaire de chaînes personnalisé pour réaffecter la mémoire tampon.  Lorsque allouer ou réaffecter une structure d' `CStringData` , vous devez définir ce champ au moins le nombre de caractères demandés dans le paramètre de **nChars** à [IAtlStringMgr::Allocate](../Topic/IAtlStringMgr::Allocate.md) ou à [IAtlStringMgr::Reallocate](../Topic/IAtlStringMgr::Reallocate.md).  S'il y a plus d'espace dans la mémoire tampon que demandé, vous pouvez définir cette valeur pour refléter la quantité actuel de l'espace disponible.  Cela permet à `CStringT` pour élever la chaîne pour remplir l'espace alloué entier avant qu'il ait appeler dans le gestionnaire de chaînes à réaffecter la mémoire tampon.  
  
-   [nRefs](../Topic/CStringData::nRefs.md) ce champ contient le nombre de références actuel de la mémoire tampon de chaîne.  Si la valeur est une, une seule instance d' `CStringT` utilise la mémoire tampon.  En outre, l'instance est autorisé à lire et modifie le contenu de la mémoire tampon.  Si la valeur est supérieure à une, plusieurs instances d' `CStringT` peuvent utiliser la mémoire tampon.  Étant donné que la mémoire tampon de caractères est partagé, les instances d' `CStringT` peuvent seulement lire le contenu de la mémoire tampon.  Pour modifier le contenu, `CStringT` tire d'abord une copie de la mémoire tampon.  Si la valeur est négative, une seule instance d' `CStringT` utilise la mémoire tampon.  Dans ce cas, la mémoire tampon est considérée comme verrouillée.  Lorsqu'une instance d' `CStringT` utilise une mémoire tampon verrouillée pas d'autres instances d' `CStringT` peuvent partager la mémoire tampon.  À la place, ces instances crée une copie de la mémoire tampon avant de manipuler le contenu.  En outre, l'instance d' `CStringT` utilisation de la mémoire tampon verrouillée ne tente pas de partager la mémoire tampon d'aucune autre instance d' `CStringT` assignée à celui\-ci.  Dans ce cas, l'instance d' `CStringT` copie l'autre chaîne dans la mémoire tampon verrouillée.  
  
     En allouant une structure d' `CStringData` , vous devez définir ce champ pour refléter le partage de type autorisé pour la mémoire tampon.  Pour la plupart des implémentations, définissez cette valeur à une.  Cela permet le comportement habituel de partage de copie\-sur\- Écriture.  Toutefois, si votre gestionnaire de chaînes ne prend pas partager la mémoire tampon de chaîne, définissez ce champ à un état verrouillé.  Cela force `CStringT` pour utiliser uniquement cette mémoire tampon pour l'instance d' `CStringT` qui l'a allouée.  
  
## Voir aussi  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)