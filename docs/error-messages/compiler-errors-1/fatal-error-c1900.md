---
title: "Erreur irrécupérable C1900 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1900
dev_langs: C++
helpviewer_keywords: C1900
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3b64061401189fb37f28492fbffe1e9941e8aab8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1900"></a>Erreur irrécupérable C1900
Incompatibilité IL de 'outil1' version 'numéro1' et 'outil2' version 'numéro2'  
  
 Les outils exécutés dans différentes passes du compilateur ne correspondent pas. ***number1*** et ***number2*** font référence aux dates sur les fichiers. Par exemple, dans la passe 1, le compilateur frontal s'exécute (c1.dll), alors que dans la passe 2, c'est le compilateur principal (c2.dll). Les dates doivent correspondre dans les fichiers.  
  
 Pour résoudre ce problème, assurez-vous que toutes les mises à jour ont été appliquées à Visual Studio. Si le problème persiste, utilisez **programmes et fonctionnalités** dans le panneau de configuration Windows pour réparer ou réinstaller Visual Studio.