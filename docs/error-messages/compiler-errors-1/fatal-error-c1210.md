---
title: "Erreur irrécupérable C1210 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1210
dev_langs:
- C++
helpviewer_keywords:
- C1210
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: f3abd56aebdf7e83bbab10b6083ad6fc14987fbd
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1210"></a>Erreur irrécupérable C1210
/clr:pure et /clr:safe ne sont pas pris en charge par la version installée du runtime  
  
 Le **/CLR : pure** et **/CLR : safe** options du compilateur sont déconseillées dans Visual Studio 2015.  
  
 L’erreur C1210 se produit quand vous avez un compilateur pour la version actuelle, mais un Common Language Runtime d’une version précédente.  
  
 Certaines fonctionnalités du compilateur risquent de ne pas fonctionner sur une version précédente du runtime.  
  
 Pour remédier à l’erreur C1210, installez la version du Common Language Runtime prévue pour votre compilateur.
