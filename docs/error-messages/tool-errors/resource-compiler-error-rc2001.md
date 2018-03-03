---
title: Erreur RC2001 du compilateur de ressources | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c04110898780495f918c1e37c0068daead340a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2001"></a>Erreur RC2001 du compilateur de ressources 
saut de ligne dans la constante  
  
 Une constante de chaîne se poursuivie sur une seconde ligne, sans utilisation d’une barre oblique inverse (**\\**) ou ouverture et fermeture des guillemets doubles (**»**).  
  
 Pour interrompre une constante de chaîne sur deux lignes dans le fichier source, effectuez l’une des opérations suivantes :  
  
-   Fin de la première ligne avec le caractère de continuation de ligne, une barre oblique inverse.  
  
-   Fermez la chaîne sur la première ligne par un guillemet double et ouvrez la chaîne sur la ligne suivante avec un autre guillemet.  
  
 Il n’est pas suffisant mettre fin à la première ligne par \n, la séquence d’échappement pour incorporer un caractère de saut de ligne dans une constante de chaîne.