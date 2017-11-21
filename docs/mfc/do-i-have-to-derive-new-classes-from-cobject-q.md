---
title: "Dois-je dériver les nouvelles classes de CObject ? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CObject
dev_langs: C++
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 10254dbfe4f8db61aebfaa934d86adee36b64c83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>Dois-je dériver les nouvelles classes de CObject ?
Non, vous n’avez pas.  
  
 Dérivez une classe de [CObject](../mfc/reference/cobject-class.md) lorsque vous avez besoin des fonctionnalités qu’il fournit, telles que la sérialisation ou de la création dynamique d’objets. De nombreuses classes de données doivent être sérialisés dans des fichiers, il est souvent judicieux de les dériver de `CObject`. Pour obtenir un exemple d’une classe dérivée de `CObject`, consultez la [exemple Scribble](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Classe CObject : Forum Aux Questions](../mfc/cobject-class-frequently-asked-questions.md)
