---
title: "LNK1106 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1106
dev_langs: C++
helpviewer_keywords: LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b97196ebed51c21e40fa74ab1b80d23f3c49eec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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