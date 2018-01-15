---
title: "TN032 : Mécanisme d’Exception MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.exceptions
dev_langs: C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf82d4b158cedd2d8f6916dfb01d26db6c62d83b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032 : mécanisme d'exception MFC
Les versions précédentes de Visual C++ ne prenait pas en charge le mécanisme d’exception C++ standard, et MFC fournie macros **TRY/CATCH/THROW** qui ont été utilisées à la place. Cette version de Visual C++ prend entièrement en charge les exceptions C++. Cette note couverts certains aspects de l’implémentation avancée des macros précédentes, y compris comment automatiquement les objets de pile en fonction de nettoyage. Exceptions C++ prenant en charge la pile le déroulement par défaut, cette note technique n’est plus nécessaire.  
  
 Reportez-vous à [Exceptions : utilisation des Macros MFC et des Exceptions C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) pour plus d’informations sur les différences entre les macros MFC et les nouveaux mots clés C++.  
  
## <a name="see-also"></a>Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)

