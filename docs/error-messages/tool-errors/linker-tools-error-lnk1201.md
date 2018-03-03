---
title: "LNK1201 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1201
dev_langs:
- C++
helpviewer_keywords:
- LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44e2ad811645889cd655bf297f6f8b9492574def
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1201"></a>Erreur des outils Éditeur de liens LNK1201
Erreur d’écriture dans la base de données du programme 'NomFichier' ; Recherchez un espace disque insuffisant, un chemin non valide ou privilège insuffisant  
  
 LIEN n’a pas pu écrire dans la base de données de programme (PDB) pour le fichier de sortie.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Fichier est endommagé. Supprimer le fichier PDB et relier.  
  
2.  Espace disque insuffisant pour écrire le fichier.  
  
3.  Lecteur n’est pas disponible, probablement en raison d’un problème réseau.  
  
4.  Le débogueur est actif sur le programme que vous essayez de lier.  
  
5.  Espace du tas insuffisant.  Consultez [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) pour plus d’informations.