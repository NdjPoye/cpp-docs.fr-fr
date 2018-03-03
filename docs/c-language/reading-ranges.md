---
title: Lecture des plages | Microsoft Docs
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
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36fd3354e21b063dba05e24e1e3ba0d206a89343
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="reading-ranges"></a>Lecture des plages
**ANSI 4.9.6.2** L’interprétation d’un tiret (-) qui n’est ni le premier ni le dernier caractère de la scanlist pour la conversion % [ dans la fonction `fscanf`  
  
 La ligne suivante  
  
```  
fscanf( fileptr, "%[A-Z]", strptr);  
```  
  
 lit tout nombre de caractères dans la plage A-Z dans la chaîne vers laquelle pointe `strptr`.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)