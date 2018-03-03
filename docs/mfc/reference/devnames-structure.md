---
title: DEVNAMES, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEVNAMES
dev_langs:
- C++
helpviewer_keywords:
- DEVNAMES [MFC]
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a3627af10dfb6fd18c54f772d26c33123127613a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="devnames-structure"></a>DEVNAMES, structure
Le `DEVNAMES` structure contient des chaînes qui identifient le pilote, appareil et les noms de port de sortie d’une imprimante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagDEVNAMES { /* dvnm */  
    WORD wDriverOffset;  
    WORD wDeviceOffset;  
    WORD wOutputOffset;  
    WORD wDefault; */* driver,
    device,
    and port-name strings follow wDefault */  
} DEVNAMES;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *wDriverOffset*  
 (Entrée/sortie) Spécifie le décalage de caractères en une chaîne terminée par le caractère null qui contient le nom de fichier (sans l’extension) du pilote de périphérique. En entrée, cette chaîne est utilisée pour déterminer l’imprimante à afficher initialement dans la boîte de dialogue.  
  
 *wDeviceOffset*  
 (Entrée/sortie) Spécifie le décalage de caractères à la chaîne se terminant par null (maximum de 32 octets, y compris la valeur null) qui contient le nom de l’appareil. Cette chaîne doit être identique à la **dmDeviceName** membre de la [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) structure.  
  
 *wOutputOffset*  
 (Entrée/sortie) Spécifie le décalage de caractères à la chaîne se terminant par null qui contient le nom de périphérique DOS pour la sortie physique du port de sortie.  
  
 *wDefault*  
 Spécifie si les chaînes contenues dans le `DEVNAMES` structure identifier l’imprimante par défaut. Cette chaîne est utilisée pour vérifier que l’imprimante par défaut n’a pas changé depuis la dernière opération d’impression. En entrée, si le **DN_DEFAULTPRN** indicateur est défini, les autres valeurs dans le `DEVNAMES` structure sont vérifiées par rapport à l’imprimante par défaut en cours. Si aucune de ces chaînes ne correspondent pas, un message d’avertissement s’affiche pour informer l’utilisateur qui doivent être remises en forme le document. En sortie, le **wDefault** membre est modifié uniquement si la boîte de dialogue Configuration de l’impression est affichée et l’utilisateur a choisi le bouton OK. Le **DN_DEFAULTPRN** indicateur est défini si l’imprimante par défaut a été sélectionnée. Si une imprimante spécifique est sélectionnée, l’indicateur n’est pas défini. Tous les autres bits dans ce membre sont réservés à un usage interne par la procédure de boîte de dialogue d’impression.  
  
## <a name="remarks"></a>Notes  
 Le **PrintDlg** fonction utilise ces chaînes pour initialiser les membres dans la boîte de dialogue Imprimer définies par le système. Lorsque l’utilisateur ferme la boîte de dialogue, les informations sur l’imprimante sélectionnée sont retournées dans cette structure.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** commdlg.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)


