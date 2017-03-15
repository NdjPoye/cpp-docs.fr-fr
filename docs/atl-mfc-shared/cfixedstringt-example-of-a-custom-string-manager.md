---
title: "CFixedStringT: Example of a Custom String Manager | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT class, using a custom string manager"
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CFixedStringT: Example of a Custom String Manager
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque ATL implémente un exemple d'un gestionnaire de chaînes personnalisé utilisé par la classe [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md), **CFixedStringMgr**appelé.  `CFixedStringT` est dérivé de [CStringT](../atl-mfc-shared/reference/cstringt-class.md) et implémente une chaîne qui alloue ses données caractères dans le cadre de l'objet d' `CFixedStringT` elle\-même forme de la chaîne est inférieure à la longueur spécifiée par le paramètre de modèle de **t\_nChars** d' `CFixedStringT`.  Avec cette approche, la chaîne n'a pas besoin du tas du tout, à moins que la longueur de la chaîne se développe au delà de la taille de la mémoire tampon fixe.  Étant donné qu' `CFixedStringT` n'utilise pas toujours un tas à allouer ses données de chaîne, il ne peut pas utiliser **CAtlStringMgr** comme gestionnaire de chaînes.  Il utilise un gestionnaire de chaînes personnalisé \(**CFixedStringMgr**\), implémentant l'interface d' [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) .  Cette interface est décrite dans [Implémentation d'un gestionnaire de chaînes personnalisé \(méthode avancée\)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md).  
  
 Le constructeur pour **CFixedStringMgr** prend trois paramètres :  
  
-   Pointeur de**pData:** à la structure fixe d' `CStringData` à utiliser.  
  
-   **nChars:** le nombre maximal de caractères que la structure d' `CStringData` peut contenir.  
  
-   Pointeur de**pMgr:** à l'interface d' `IAtlStringMgr` « d'un gestionnaire de chaînes de sauvegarde. »  
  
 Le constructeur stocke les valeurs d' `pData` et de **pMgr** dans leurs variables membres respectives \(`m_pData` et **m\_pMgr**\).  Il définit ensuite la longueur de la mémoire tampon à zéro, la longueur est égale à la taille maximale de la mémoire tampon fixe, et le décompte de références – à 1.  La valeur de décompte de références indique la mémoire tampon est verrouillée et pour utiliser cette instance de **CFixedStringMgr** en tant que gestionnaire de chaînes.  
  
 Marquer la mémoire tampon comme verrouillé empêché d'autres instances d' `CStringT` de stocker une référence partagée dans la mémoire tampon.  Si vous permettait à d'autres instances d' `CStringT` pour partager la mémoire tampon il est possible pour la mémoire tampon contenue par `CFixedStringT` à effacer tandis que d'autres chaînes utilisaient toujours la mémoire tampon.  
  
 **CFixedStringMgr** est une implémentation complète de l'interface d' `IAtlStringMgr` .  L'implémentation de chaque méthode est abordée séparément.  
  
## Implémentation de CFixedStringMgr::Allocate  
 L'implémentation de **CFixedStringMgr::Allocate** vérifie d'abord si la taille demandée de la chaîne est inférieure ou égale à la taille de la mémoire tampon fixe \(stocké dans le membre d' `m_pData` \).  Si la mémoire tampon fixe est suffisamment grande, **CFixedStringMgr** verrouille la mémoire tampon fixe d'une longueur égale à zéro.  Tant que la longueur de chaîne ne développe pas au delà de la taille de la mémoire tampon fixe, `CStringT` n'aura pas réaffecter la mémoire tampon.  
  
 Si la taille demandée de la chaîne est supérieure à la mémoire tampon fixe **CFixedStringMgr** transféré à la demande le gestionnaire de chaînes de sauvegarde.  Le gestionnaire de chaînes d'enregistrement est présumé pour allouer de la mémoire tampon du tas.  Toutefois, avant de retourner cette mémoire tampon **CFixedStringMgr** verrouille la mémoire tampon et remplace le pointeur du gestionnaire de chaînes de la mémoire tampon avec un pointeur vers l'objet de **CFixedStringMgr** .  Cela garantit que les tentatives de réaffecter ou libérer la mémoire tampon par `CStringT` appellent dans **CFixedStringMgr**.  
  
## Implémentation de CFixedStringMgr::ReAllocate  
 L'implémentation de **CFixedStringMgr::ReAllocate** est très similaire à son implémentation d' **Allocate**.  
  
 Si la mémoire tampon qui est réaffectée est la mémoire tampon fixe et la taille de mémoire tampon demandée est inférieure à la mémoire tampon fixe, aucune allocation n'est effectuée.  Toutefois, si la mémoire tampon qui est réaffectée n'est pas la mémoire tampon fixe, il doit s'agir d'une mémoire tampon allouée avec le gestionnaire de sauvegarde.  Dans ce cas le gestionnaire de sauvegarde est utilisé pour réaffecter la mémoire tampon.  
  
 Si la mémoire tampon qui est réaffectée est la mémoire tampon fixe et la nouvelle taille de mémoire tampon est trop grande pour entrer dans la mémoire tampon fixe, **CFixedStringMgr** alloue une nouvelle mémoire tampon à l'aide de le gestionnaire de sauvegarde.  Le contenu de la mémoire tampon fixe est ensuite copié vers la nouvelle mémoire tampon.  
  
## Implémentation de CFixedStringMgr::Free  
 L'implémentation de **CFixedStringMgr::Free** suit le même modèle que **Allocate** et `ReAllocate`.  Si la mémoire tampon est libérée est la mémoire tampon fixe, la méthode la place dans une mémoire tampon verrouillée de longueur zéro.  Si la mémoire tampon est libérée est allouée avec le gestionnaire de sauvegarde, **CFixedStringMgr** utilise le gestionnaire de sauvegarde pour le libérer.  
  
## Implémentation de CFixedStringMgr::Clone  
 L'implémentation de **CFixedStringMgr::Clone** retourne toujours un pointeur vers le gestionnaire de sauvegarde plutôt que **CFixedStringMgr** elle\-même.  Cela se produit parce que chaque instance de **CFixedStringMgr** peut être associée à une instance unique d' `CStringT`.  Toutes les autres instances d' `CStringT` une tentative de cloner le gestionnaire doit obtenir le gestionnaire de sauvegarde à la place.  C'est parce que le support de sauvegarde de gestionnaire qui sont partagés.  
  
## Implémentation de CFixedStringMgr::GetNilString  
 L'implémentation de **CFixedStringMgr::GetNilString** retourne la mémoire tampon fixe.  En raison de la correspondance face à face de **CFixedStringMgr** et d' `CStringT`, une instance donnée d' `CStringT` n'utilise à la fois jamais plusieurs mémoire tampon.  Par conséquent, une chaîne de zéro et une vraie mémoire tampon de chaîne ne sont jamais en même temps nécessaire.  
  
 Chaque fois que la mémoire tampon fixe est pas utilisée, **CFixedStringMgr** garantit qu'il est initialisé avec une longueur égale à zéro.  Cela lui permet à utiliser comme une chaîne de zéro.  Comme bonification ajoutée, le membre d' `nAllocLength` de la mémoire tampon fixe est toujours placé à la taille totale de la mémoire tampon fixe.  Cela signifie qu' `CStringT` peut élever la chaîne sans appeler [IAtlStringMgr::Reallocate](../Topic/IAtlStringMgr::Reallocate.md), même pour la chaîne à zéro.  
  
## Configuration requise  
 **Header:** cstringt.h  
  
## Voir aussi  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)