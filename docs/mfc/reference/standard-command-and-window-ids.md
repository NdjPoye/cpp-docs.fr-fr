---
title: ID de fenêtre et commande standard | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72b50108a9b880961f0dd8bcded1126a635fb9e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="standard-command-and-window-ids"></a>ID de fenêtre et commande standard
La bibliothèque Microsoft Foundation Class définit un numéro d’ID de fenêtre et commande standard dans Afxres.h. Ces ID est couramment utilisés dans les éditeurs de ressources et de la fenêtre Propriétés pour mapper les messages à vos fonctions gestionnaires. Toutes les commandes standards ont une **ID_** préfixe. Par exemple, lorsque vous utilisez l’éditeur de menus, vous normalement liez l’élément de menu Ouvrir le fichier à la norme `ID_FILE_OPEN` ID de commande.  
  
 Pour la plupart des commandes, code d’application est inutile faire référence à l’ID de commande, car l’infrastructure elle-même gère les commandes à travers des tables des messages dans ses classes framework principal ( `CWinThread`, `CWinApp`, < c4 > `CView` , **CDocument**, et ainsi de suite).  
  
 En plus de l’ID de commande standard, un nombre d’autres identificateurs standards est défini qui ont un préfixe de **AFX_ID**. Ces ID est des ID de fenêtre standard (préfixe **AFX_IDW_**), ID de chaîne (préfixe **AFX_IDS_**) et plusieurs autres types.  
  
 ID qui commencent par le **AFX_ID** préfixe sont rarement utilisées par les programmeurs, mais vous devrez peut-être faire référence à ces ID lors de la substitution des fonctions de framework également faire référence à la **AFX_ID**s.  
  
 Les ID ne sont pas documentées individuellement dans cette référence. Vous trouverez plus d’informations sur ces derniers dans les Notes techniques [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), et [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  Le fichier d’en-tête Afxres.h est indirectement inclus dans Afxwin.h. Vous devez inclure explicitement l’instruction suivante dans le fichier de script (.rc) de ressources de votre application :  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
