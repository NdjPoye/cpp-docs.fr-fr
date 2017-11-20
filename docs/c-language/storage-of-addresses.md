---
title: Stockage des adresses | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3d0e996ac191ba3091925a85937e7636a2425215
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="storage-of-addresses"></a>Stockage des adresses
La quantité de stockage requis pour une adresse et la signification de l'adresse dépendent de l'implémentation du compilateur. Les pointeurs vers des types différents ne sont pas garantis avoir la même longueur. Par conséquent, **sizeof(char \*)** n'est pas nécessairement égal à **sizeof(int \*)**.  
  
 **Section spécifique à Microsoft**  
  
 Pour le compilateur C Microsoft, **sizeof(char \*)** est égal à **sizeof(int \*)**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Déclarations de pointeur](../c-language/pointer-declarations.md)