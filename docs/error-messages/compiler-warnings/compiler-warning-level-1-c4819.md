---
title: Compilateur avertissement (niveau 1) C4819 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4819
dev_langs:
- C++
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b515a3f5e840bbc93f37420866023ee778b404ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4819"></a>Avertissement du compilateur (niveau 1) C4819
Le fichier contient un caractère qui ne peut pas être représenté dans la page de codes actuelle (numéro). Enregistrez le fichier au format Unicode pour éviter toute perte de données.  
  
 L'erreur C4819 se produit quand un fichier source ANSI est compilé sur un système avec une page de codes qui ne peut pas représenter tous les caractères compris dans le fichier.  
  
 Pour résoudre l'erreur C4819, enregistrez le fichier au format Unicode. Dans Visual Studio, choisissez **fichier**, **Options d’enregistrement avancées**. Dans le **Options d’enregistrement avancées** boîte de dialogue, sélectionnez un encodage qui peut représenter tous les caractères dans le fichier : par exemple, UTF-8, puis choisissez **OK**.