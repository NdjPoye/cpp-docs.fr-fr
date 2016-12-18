---
title: "Concurrency::direct3d, espace de noms | Microsoft Docs"
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
  - "amp/Concurrency::direct3d"
  - "amprt/Concurrency::direct3d"
  - "amp_short_vectors/Concurrency::direct3d"
  - "amp_graphics/Concurrency::direct3d"
  - "amp_math/Concurrency::direct3d"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "direct3d (espace de noms)"
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency::direct3d, espace de noms
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

L'espace de noms `direct3d` fournit les fonctions qui prennent en charge l'interopérabilité D3D.  Il permet d'utiliser de façon transparente les ressources D3D pour le calcul dans le code AMP ainsi que l'utilisation des ressources créées dans AMP dans le code D3D, sans créer des copies intermédiaires redondantes.  Vous pouvez accélérer les sections intensives de calcul de façon incrémentielle de vos applications DirectX à l'aide de C\+\+ AMP et de l'API D3D sur les données générées par des calculs AMP.  
  
## Syntaxe  
  
```  
namespace direct3d;  
```  
  
## Membres  
  
### Classes  
  
|Nom|Description|  
|---------|-----------------|  
|[scoped\_d3d\_access\_lock, classe](../../../parallel/amp/reference/scoped-d3d-access-lock-class.md)|Wrapper RAII pour verrou d'accès D3D sur un objet `accelerator_view`.|  
  
### Structures  
  
|Nom|Description|  
|---------|-----------------|  
|[adopt\_d3d\_access\_lock\_t, structure](../../../parallel/amp/reference/adopt-d3d-access-lock-t-structure.md)|Type de balise pour indiquer que le verrou d'accès D3D doit être adopté plutôt qu'interrompu.|  
  
### Fonctions  
  
|Nom|Description|  
|---------|-----------------|  
|[abs, fonction](../Topic/abs%20Function.md)|Retourne la valeur absolue de l'argument|  
|[clamp, fonction](../Topic/clamp%20Function.md)|Surchargé.  Fixe \_X à la plage \_Min et \_Max spécifiée|  
|[countbits, fonction](../Topic/countbits%20Function.md)|Compte le nombre de bits de positionnement dans \_X|  
|[create\_accelerator\_view, fonction](../Topic/create_accelerator_view%20Function.md)|Crée une [accelerator\_view, classe](../../../parallel/amp/reference/accelerator-view-class.md) à partir d'un pointeur vers une interface de périphérique Direct3D|  
|[d3d\_access\_lock, fonction](../Topic/d3d_access_lock%20Function.md)|Acquiert un verrou sur un accelerator\_view pour exécuter sans risque les opérations D3D sur les ressources partagées avec l'accelerator\_view|  
|[d3d\_access\_try\_lock, fonction](../Topic/d3d_access_try_lock%20Function.md)|Tentative d'acquisition du verrou d'accès D3D sur un accelerator\_view sans blocage.|  
|[d3d\_access\_unlock, fonction](../Topic/d3d_access_unlock%20Function.md)|Relâche le verrou d'accès D3D sur l'accelerator\_view donné.|  
|[firstbithigh, fonction](../Topic/firstbithigh%20Function.md)|Obtient l'emplacement du premier bit défini dans \_X, du bit le plus haut vers le plus bas|  
|[firstbitlow, fonction](../Topic/firstbitlow%20Function.md)|Obtient l'emplacement du premier bit défini dans \_X, en allant du bit le moins significatif au bit le plus significatif.|  
|[get\_buffer, fonction](../Topic/get_buffer%20Function.md)|Obtient l'interface de mémoire tampon D3D sous\-jacente d'un tableau.|  
|[imax, fonction](../Topic/imax%20Function.md)|Compare deux valeurs, en retournant la valeur la plus élevée.|  
|[imin, fonction](../Topic/imin%20Function.md)|Compare deux valeurs, en retournant la valeur la plus faible.|  
|[is\_timeout\_disabled, fonction](../Topic/is_timeout_disabled%20Function.md)|Retourne un indicateur booléen indiquant si le délai d'attente est désactivé pour l'accelerator\_view spécifié.|  
|[mad, fonction](../Topic/mad%20Function.md)|Surchargé.  Effectue une opération arithmétique multiplication\/addition sur trois arguments : \_X \* \_Y \+ \_Z|  
|[make\_array, fonction](../Topic/make_array%20Function.md)|Créez un tableau à partir d'un pointeur d'interface de mémoire tampon D3D.|  
|[noise, fonction](../Topic/noise%20Function.md)|Génère une valeur aléatoire à l'aide de l'algorithme de bruit de Perlin|  
|[radians, fonction](../Topic/radians%20Function.md)|Convertit \_X de degrés en radians|  
|[rcp, fonction](../Topic/rcp%20Function.md)|Calcule une réciproque rapide et approximative de l'argument|  
|[reversebits, fonction](../Topic/reversebits%20Function.md)|Inverse l'ordre des bits dans \_X|  
|[saturate, fonction](../Topic/saturate%20Function.md)|Fixe \_X dans la plage de 0 à 1|  
|[sign, fonction](../Topic/sign%20Function.md)|Surchargé.  Retourne le signe de l'argument|  
|[smoothstep, fonction](../Topic/smoothstep%20Function.md)|Retourne une interpolation Hermite fluide entre 0 et 1, si \_X se situe dans la plage \[\_Min, \_Max\].|  
|[step, fonction](../Topic/step%20Function.md)|Compare deux valeurs, retourne 0 ou 1 suivant laquelle est supérieure|  
|[umax, fonction](../Topic/umax%20Function.md)|Compare deux valeurs non signées, en retournant la valeur la plus élevée.|  
|[umin, fonction](../Topic/umin%20Function.md)|Compare deux valeurs non signées, en retournant la valeur la plus faible.|  
  
## Configuration requise  
 **En\-tête :** amp.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)