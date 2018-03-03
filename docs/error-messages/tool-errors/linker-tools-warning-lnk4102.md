---
title: "LNK4102 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4102
dev_langs:
- C++
helpviewer_keywords:
- LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80efad60da9f6742110811a5cf4c12f07c7def67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4102"></a>Avertissement des outils Éditeur de liens LNK4102
exportation de la suppression de destructeur 'nom' ; image peut ne pas fonctionne correctement  
  
 Le programme a tenté d’exporter un destructeur de suppression. La suppression qui en résulte peut se produire sur une limite DLL telles qu’un processus peut libérer de la mémoire qu’il ne possède pas. Assurez-vous que le symbole donné n’est pas répertorié dans le fichier .def, et que le symbole n’est pas répertorié en tant qu’argument de la **/importation** ou **/EXPORT** option dans la ligne de commande de l’éditeur de liens.  
  
 Si vous régénérez la bibliothèque Runtime C, vous pouvez ignorer ce message.