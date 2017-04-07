---
title: Concurrency::Direct3D Namespace | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
dev_langs:
- C++
helpviewer_keywords:
- direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 94e0542910484166a01bd79beb9dfaa805aae6cd
ms.lasthandoff: 03/17/2017

---
# <a name="concurrencydirect3d-namespace"></a>Concurrency::direct3d, espace de noms
Le `direct3d` espace de noms fournit des fonctions qui prennent en charge l’interopérabilité D3D. Il permet une utilisation transparente D3D ressources de calcul dans le code de l’AMP ainsi autoriser l’utilisation de ressources créées dans le code D3D, de gestion du matériel sans créer des copies redondantes intermédiaires. Vous pouvez progressivement accélérer les sections intensif de calcul de vos applications DirectX à l’aide de C++ AMP et utiliser l’API D3D sur les données générées à partir de calculs AMP.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
namespace direct3d;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="classes"></a>Classes  
  
|Nom|Description|  
|----------|-----------------|  
|[scoped_d3d_access_lock, classe](scoped-d3d-access-lock-class.md)|Un wrapper RAII pour un verrou d’accès D3D sur un `accelerator_view` objet.|  
  
### <a name="structures"></a>Structures  
  
|Nom|Description|  
|----------|-----------------|  
|[adopt_d3d_access_lock_t, structure](adopt-d3d-access-lock-t-structure.md)|Type de balise pour indiquer le verrou d’accès D3D doit être adoptée plutôt qu’acquises.|  
  
### <a name="functions"></a>Fonctions  
  
|Nom|Description|  
|----------|-----------------|  
|[abs](concurrency-direct3d-namespace-functions-amp.md#abs)|Retourne la valeur absolue de l’argument|  
|[Clamp](concurrency-direct3d-namespace-functions-amp.md#clamp)|Surchargé. Crochets _X à la plage spécifiée de _Min et de _Max|  
|[countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|Compte le nombre de bits de jeu dans _X|  
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Crée un [accelerator_view, classe](accelerator-view-class.md) d’un pointeur vers une interface de périphérique Direct3D|  
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Acquiert un verrou sur une accelerator_view pour les besoins en toute sécurité des opérations D3D ressources partagées entre les accelerator_view|  
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|Tenter d’acquérir le verrou d’accès D3D sur une accelerator_view sans se bloquer.|  
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Déverrouiller l’accès D3D l’accelerator_view donné.|  
|[firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|Obtient l’emplacement du premier bit ensemble dans _X, commençant par le bit d’ordre le plus élevé et d’utilisation vers le bas|  
|[firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|Obtient l’emplacement du premier bit ensemble dans _X, commençant par le bit d’ordre le plus bas et d’utilisation vers le haut|  
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Obtenir l’interface de mémoire tampon D3D sous-jacent d’un tableau.|  
|[Imax](concurrency-direct3d-namespace-functions-amp.md#imax)|Compare deux valeurs, en retournant la valeur supérieure.|  
|[Imin](concurrency-direct3d-namespace-functions-amp.md#imin)|Compare deux valeurs, en retournant la valeur qui est plus petite.|  
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Retourne un indicateur booléen indiquant si le délai d’attente est désactivée pour l’accelerator_view spécifié.|  
|[MAD](concurrency-direct3d-namespace-functions-amp.md#mad)|Surchargé. Effectue une opération de multiplication/addition arithmétique sur trois arguments : _X * _Y + _Z|  
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|Créer un tableau à partir d’un pointeur d’interface de mémoire tampon D3D.|  
|[bruit](concurrency-direct3d-namespace-functions-amp.md#noise)|Génère une valeur aléatoire à l’aide de l’algorithme de bruit Perlin|  
|[radians](concurrency-direct3d-namespace-functions-amp.md#radians)|Convertit _X de degrés en radians|  
|[rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|Calcule un réciproque rapide et approximative de l’argument|  
|[reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|Inverse l’ordre des octets dans _X|  
|[saturer](concurrency-direct3d-namespace-functions-amp.md#saturate)|Crochets _X dans la plage de 0 à 1.|  
|[connexion](concurrency-direct3d-namespace-functions-amp.md#sign)|Surchargé. Retourne le signe de l’argument|  
|[smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|Renvoie une interpolation d’Hermite lisse entre 0 et 1, si _X se trouve dans la plage [_Min, _Max].|  
|[étape](concurrency-direct3d-namespace-functions-amp.md#step)|Compare deux valeurs de retour de 0 ou 1 selon que la valeur est supérieure|  
|[UMAX](concurrency-direct3d-namespace-functions-amp.md#umax)|Compare deux valeurs non signées, retournant la valeur supérieure.|  
|[umin](concurrency-direct3d-namespace-functions-amp.md#umin)|Compare deux valeurs non signées, retournant la valeur qui est plus petite.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** amp.h  
  
 **Espace de noms :** Concurrency  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency, espace de noms (C++ AMP)](concurrency-namespace-cpp-amp.md)

