---
title: "PRJ0050 d’erreur de Build de projet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0050
dev_langs:
- C++
helpviewer_keywords:
- PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e9d9b123da2e32db0f695c31bc9643a481d352b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0050"></a>Erreur de génération de projet PRJ0050
Échec de l’inscription de la sortie. Vérifiez que vous disposez des autorisations appropriées pour modifier le Registre.  
  
 Le système de génération Visual C++ n’a pas pu enregistrer la sortie de la build (dll ou .exe). Vous devez avoir ouvert une session en tant qu’administrateur pour modifier le Registre.  
  
 Si vous générez un fichier .dll, vous pouvez essayer d’inscrire le fichier .dll manuellement à l’aide de regsvr32.exe, il doit afficher des informations sur la raison pour laquelle la génération a échoué.  
  
 Si vous ne créez pas un fichier .dll, examinez le journal de génération de la commande qui provoque une erreur.