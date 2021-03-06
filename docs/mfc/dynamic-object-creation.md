---
title: Création d’objet dynamique | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5763e3f0f3ee5a0e58ac20fe9f637e4f7e097999
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="dynamic-object-creation"></a>Création d'objet dynamique
Cet article explique comment créer un objet dynamiquement au moment de l’exécution. La procédure utilise les informations de classe d’exécution, comme indiqué dans l’article [l’accès aux informations de classe d’exécution](../mfc/accessing-run-time-class-information.md).  
  
#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>Pour créer dynamiquement un objet en fonction de sa classe d’exécution  
  
1.  Utilisez le code suivant pour créer dynamiquement un objet à l’aide de la `CreateObject` fonction de la `CRuntimeClass`. Notez qu’en cas d’échec, `CreateObject` retourne **NULL** au lieu de déclencher une exception :  
  
     [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CObject](../mfc/using-cobject.md)

