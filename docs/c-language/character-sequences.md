---
title: "Séquences de caractères | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09134a17ad8711169a3afc30490c188af47a3f42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="character-sequences"></a>Séquences de caractères
**ANSI 3.8.2** Mappage des séquences de caractères de fichier source  
  
 Les instructions de préprocesseur utilisent le même jeu de caractères que les instructions de fichier source, sauf que les séquences d'échappement ne sont pas prises en charge.  
  
 Ainsi, pour spécifier le chemin d'accès d'un fichier Include, utilisez une seule barre oblique inverse :  
  
```  
#include "path1\path2\myfile"  
```  
  
 Dans le code source, deux barres obliques inverses sont nécessaires :  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Directives de prétraitement](../c-language/preprocessing-directives.md)