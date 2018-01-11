---
title: Erreur du compilateur C2338 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2338
dev_langs: C++
helpviewer_keywords: C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0171654bde5b056a7e6695ea5fbbe84edb62f83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2338"></a>Erreur du compilateur C2338  
  
> *Message d’erreur*  
  
Cette erreur peut être provoquée par un `static_assert` erreur lors de la compilation. Le message est fourni par le `static_assert` paramètres.   
  
Ce message d’erreur peut également être généré par des fournisseurs externes au compilateur. Dans la plupart des cas, ces erreurs sont signalées par un fournisseur d’attributs DLL, telle que ATLPROV. Certaines formes courantes de ce message sont les suivantes :

> '*attribut*' Atl Attribute Provider : erreur ATL*nombre* *message*  
  
> Utilisation incorrecte de l’attribut '*attribut*'
  
> '*utilisation*' : format incorrect pour l’attribut 'utilisation'  
  
Ces erreurs sont souvent irrécupérables et peuvent être suivies d’une erreur irrécupérable du compilateur.  
  
Pour résoudre ces problèmes, corrigez l’utilisation d’attributs. Par exemple, dans certains cas, des paramètres d’attribut doivent être déclarés avant de pouvoir être utilisés. Si un numéro d’erreur ATL est fourni, consultez la documentation de cette erreur pour plus d’informations.  
