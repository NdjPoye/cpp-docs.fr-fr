---
title: "ID de fenêtre et commande standard | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
caps.latest.revision: 13
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: d308f3f9efc5933124460d9839a0e94fffa60b4a
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="standard-command-and-window-ids"></a>ID de fenêtre et commande standard
La bibliothèque Microsoft Foundation Class définit un numéro d’ID de fenêtre et commande standard dans Afxres.h. Ces ID sont couramment utilisés dans les éditeurs de ressources et de la fenêtre Propriétés pour mapper des messages à vos fonctions gestionnaires. Toutes les commandes standards ont un **ID_** préfixe. Par exemple, lorsque vous utilisez l’éditeur de menu, vous normalement liez l’élément de menu Ouvrir le fichier à la norme `ID_FILE_OPEN` ID de commande.  
  
 Pour la plupart des commandes, les code d’application ne doit pas faire référence à l’ID de commande, car l’infrastructure elle-même gère les commandes à travers des tables des messages dans ses classes framework principal ( `CWinThread`, `CWinApp`, `CView`, **CDocument**, et ainsi de suite).  
  
 En plus de l’ID de commande standard, plusieurs autres ID standard sont définis qui ont un préfixe de **AFX_ID**. Ces ID est des identificateurs de fenêtre standard (préfixe **AFX_IDW_**), ID de chaîne (préfixe **AFX_IDS_**) et plusieurs autres types.  
  
 ID qui commencent par le **AFX_ID** préfixe sont rarement utilisées par les programmeurs, mais vous devrez peut-être faire référence à ces ID lors de la substitution des fonctions de framework également faire référence à la **AFX_ID**s.  
  
 Individuellement, les ID ne sont pas documentées dans cette référence. Vous trouverez plus d’informations sur ces derniers dans les Notes techniques [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), et [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  Le fichier d’en-tête Afxres.h est indirectement inclus dans Afxwin.h. Vous devez inclure explicitement l’instruction suivante dans votre fichier de script de ressources :  
  
 [!code-cpp[NVC_MFC_Utilities&#47;](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

