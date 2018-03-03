---
title: "Contrôle de type (CRT) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.types
dev_langs:
- C++
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d18ae0818dd839bee0d93bd7194dadcc9abf6627
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="type-checking-crt"></a>Contrôle de type (CRT)
Le compilateur effectue une vérification de type limitée sur les fonctions qui peuvent prendre un nombre variable d’arguments, comme suit :  
  
|Appel de fonction |Arguments avec vérification de type|  
|-------------------|-----------------------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|Premier argument (chaîne de format)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|Deux premiers arguments (fichier ou mémoire tampon et format de chaîne)|  
|`_snprintf_s`|Trois premiers arguments (fichier ou mémoire tampon, nombre et chaîne de format)|  
|`_open`|Deux premiers arguments (chemin d’accès et indicateur `_open`)|  
|`_sopen_s`|Trois premiers arguments (chemin d’accès, indicateur `_open` et mode de partage)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|Deux premiers arguments (chemin d’accès et premier pointeur d’argument)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|Trois premiers arguments (indicateur de mode, chemin d’accès et premier pointeur d’argument)|  
  
 Le compilateur effectue la même vérification de type limitée sur les équivalents à caractères larges de ces fonctions.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctionnalités de bibliothèque CRT](../c-runtime-library/crt-library-features.md)