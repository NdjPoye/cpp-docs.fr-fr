---
title: ". Fichiers PDB en tant qu’entrée de l’éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c5acdc01a58cf0d501be5947cddf710d1b7c6d18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="pdb-files-as-linker-input"></a>Fichiers .pdb en tant qu'entrée dans l'éditeur de liens
L’objet (.obj) les fichiers compilés à l’aide de l’option/Zi contiennent le nom d’une base de données du programme (PDB). Vous ne spécifiez pas de nom de fichier PDB de l’objet à l’éditeur de liens ; LIEN utilise le nom incorporé pour trouver le fichier PDB, s’il est nécessaire. Cela s’applique également aux objets débogables contenus dans une bibliothèque ; le fichier PDB d’une bibliothèque débogable doit être disponible pour l’éditeur de liens avec la bibliothèque.  
  
 LINK utilise également un fichier PDB pour contenir les informations de débogage pour le fichier .exe ou .dll. Le PDB du programme est un fichier de sortie et un fichier d’entrée, car le lien mises à jour le fichier PDB lorsqu’il régénère le programme.  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers d’entrée LINK](../../build/reference/link-input-files.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)