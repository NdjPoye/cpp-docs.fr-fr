---
title: Structure DEVNAMES | Documents Microsoft
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
- DEVNAMES
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 698a338c94dfa402dd51fa4f683b92a5d30cc0cd
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="devnames-structure"></a>DEVNAMES, structure
Le `DEVNAMES` structure contient des chaînes qui identifient le pilote, les périphériques et les noms de port de sortie d’une imprimante.  
  
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
 (E) Spécifie le décalage de caractères en une chaîne terminée par le caractère null qui contient le nom de fichier (sans l’extension) du pilote de périphérique. En entrée, cette chaîne est utilisée pour déterminer l’imprimante à afficher initialement dans la boîte de dialogue.  
  
 *wDeviceOffset*  
 (E) Spécifie le décalage de caractères à la chaîne se terminant par null (maximum de 32 octets, y compris la valeur null) qui contient le nom de l’appareil. Cette chaîne doit être identique à la **dmDeviceName** membre de la [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) structure.  
  
 *wOutputOffset*  
 (E) Spécifie le décalage de caractères à la chaîne terminée par le caractère null qui contient le nom de périphérique DOS pour la sortie physique du port de sortie.  
  
 *wDefault*  
 Spécifie si les chaînes contenues dans le `DEVNAMES` structure identifier l’imprimante par défaut. Cette chaîne est utilisée pour vérifier que l’imprimante par défaut n’a pas changé depuis la dernière opération d’impression. En entrée, si le **DN_DEFAULTPRN** indicateur est défini, les autres valeurs dans le `DEVNAMES` structure sont vérifiées par rapport à l’imprimante par défaut. Si aucune de ces chaînes ne correspondent pas, un message d’avertissement s’affiche pour informer l’utilisateur que le document peut devoir être reformaté. En sortie, le **wDefault** membre est modifié uniquement si la boîte de dialogue Configuration de l’impression est affichée et l’utilisateur a choisi le bouton OK. Le **DN_DEFAULTPRN** est défini si l’imprimante par défaut a été sélectionnée. Si une imprimante est sélectionnée, l’indicateur n’est pas défini. Tous les autres bits dans ce membre sont réservés à un usage interne par la procédure de boîte de dialogue Imprimer.  
  
## <a name="remarks"></a>Remarques  
 Le **PrintDlg** fonction utilise ces chaînes pour initialiser les membres de la boîte de dialogue d’impression définies par le système. Lorsque l’utilisateur ferme la boîte de dialogue, les informations sur l’imprimante sélectionnée sont retournées dans cette structure.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** commdlg.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../../mfc/reference/cprintdialog-class.md#createprinterdc)



