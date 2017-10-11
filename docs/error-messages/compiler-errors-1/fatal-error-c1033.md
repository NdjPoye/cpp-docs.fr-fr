---
title: "Erreur irrécupérable C1033 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1033
dev_langs:
- C++
helpviewer_keywords:
- C1033
ms.assetid: 09976c03-8450-4cf7-8b43-1b91c2c2b9f9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a0c9c67d23f2d0b957fb3e43844245029efedc64
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1033"></a>Erreur irrécupérable C1033
Impossible d’ouvrir le fichier pdb de base de données de programme  
  
 Cette erreur peut résulter d’erreur de disque.  
  
 Dans Visual C++ .NET 2002, les paramètres régionaux utilisateur doivent être défini correctement lorsque le nom de fichier (ou le chemin d’accès de répertoire pour le nom de fichier) contient des caractères MBCS. Le fait de définir les paramètres régionaux système ne suffit pas ; vous devez configurer les paramètres régionaux utilisateur pour traiter les caractères MBCS.  
  
 Pour plus d’informations, consultez [http://support.microsoft.com/default.aspx?scid=kb;en-us;246007](http://support.microsoft.com/default.aspx?scid=kb;en-us;246007).
