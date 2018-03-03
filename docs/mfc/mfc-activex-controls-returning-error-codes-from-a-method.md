---
title: "Contrôles ActiveX MFC : Retour de Codes d’erreur à partir d’une méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5563153cdc5d90bc522c1f0b4edf48a8cc280755
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>Contrôles ActiveX MFC : retour de codes d'erreur à partir d'une méthode
Cet article décrit comment retourner des codes d’erreur à partir d’une méthode de contrôle ActiveX.  
  
 Pour indiquer qu’une erreur s’est produite dans une méthode, vous devez utiliser le [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) fonction membre, qui prend un `SCODE` (code d’état) en tant que paramètre. Vous pouvez utiliser prédéfini `SCODE` ou définir votre propre.  
  
> [!NOTE]
>  `ThrowError`est destiné à être utilisé uniquement comme un moyen de retourner une erreur à partir d’au sein Get d’une propriété ou Set fonction ou une méthode automation. Il s’agit de la seule fois où le Gestionnaire d’exceptions approprié sera présent sur la pile.  
  
 Fonctions d’assistance existent pour la plus courante prédéfinie `SCODE`s, telles que [courants ;](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), et [COleControl :: SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
 Pour obtenir la liste de prédéfinis `SCODE`s et des instructions sur la définition personnalisé `SCODE`s, consultez la section [gestion des erreurs dans votre contrôle ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) dans les contrôles ActiveX : rubriques avancées.  
  
 Pour plus d’informations sur les rapports d’exceptions dans d’autres zones de votre code, consultez [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) et la section [gestion des erreurs dans votre contrôle ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) dans les contrôles ActiveX : rubriques avancées.  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)

