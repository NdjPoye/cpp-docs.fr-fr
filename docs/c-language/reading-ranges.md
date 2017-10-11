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
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 96748c24fbf1e5adfebb72ba809533afeafebe38
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

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
