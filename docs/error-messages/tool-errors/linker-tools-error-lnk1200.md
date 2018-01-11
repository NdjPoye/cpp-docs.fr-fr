---
title: "LNK1200 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1200
dev_langs: C++
helpviewer_keywords: LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 70bf262d4f99c807e3488c1f9b2ed9e73b1eb715
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1200"></a>Erreur des outils Éditeur de liens LNK1200
Erreur de lecture de base de données du programme 'nom_fichier'  
  
 La base de données du programme (PDB) n’a pas pu être lu.  
  
 Cette erreur peut être dû à l’endommagement du fichier.  
  
 Si `filename` est le fichier PDB d’un fichier objet, recompilez le fichier objet à l’aide [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
 Si `filename` est le fichier PDB pour le fichier de sortie principal, et cette erreur s’est produite lors d’une édition de liens incrémentielle, supprimez le PDB et rétablir.