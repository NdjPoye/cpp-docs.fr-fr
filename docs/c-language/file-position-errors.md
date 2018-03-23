---
title: Erreurs de position de fichier | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1bcb4db45f17c9e2d697ee63912e63efe6e8176c
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="file-position-errors"></a>Erreurs de position de fichier
**ANSI 4.9.9.1, 4.9.9.4** Valeur à laquelle la macro `errno` est définie par la fonction `fgetpos` ou `ftell` en cas d'échec  
  
 Lorsque `fgetpos` ou `ftell` échoue, `errno` prend comme valeur la constante de manifeste `EINVAL` si la position n’est pas valide ou `EBADF` si le numéro de fichier est incorrect. Les constantes sont définies dans ERRNO.H.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)
