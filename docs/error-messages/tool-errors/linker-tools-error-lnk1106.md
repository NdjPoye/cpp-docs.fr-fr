---
title: "LNK1106 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1106
dev_langs:
- C++
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 793d788462a3a449c654c30ec874399a3bb85728
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1106"></a>Erreur des outils Éditeur de liens LNK1106
fichier non valide ou disque plein : Impossible de rechercher à l’emplacement  
  
 L’outil ne peut pas lire ou écrire sur `location` dans un fichier mappé en mémoire.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Disque plein.  
  
     Libérer de l’espace et le lier à nouveau.  
  
2.  La tentative de liaison sur un réseau.  
  
     Certains réseaux ne prennent pas entièrement en charge les fichiers mappés en mémoire utilisées par l’éditeur de liens. Essayez de liaison sur votre disque local.  
  
3.  Bloc défectueux sur le disque.  
  
     Bien que le système d’exploitation et le matériel de disque doivent avoir a détecté une telle erreur, vous voudrez exécuter un programme de vérification de disque.  
  
4.  Espace du tas insuffisant.  
  
     Consultez [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) pour plus d’informations.