---
title: "Classes partag&#233;es par MFC et ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes partagées, classes"
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes partag&#233;es par MFC et ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant répertorie les classes partagées entre MFC et ATL.  
  
|Classe|Description|Fichier d’en-tête|  
|-----------|-----------------|-----------------|  
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|Fournit des méthodes pour gérer les valeurs de date et heure associées à un fichier.|atltime.h|  
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|Fournit des méthodes pour la gestion des dates relatives et associés à un fichier de valeurs d’heure.|atltime.h|  
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|Représente un objet string avec une mémoire tampon de caractères fixe.|CStringT.h|  
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|Fournit une prise en charge améliorée des images bitmap, y compris la possibilité de charger et enregistrer des images dans les formats JPEG, GIF, BMP et PNG Portable Network Graphics ().|atlimage.h|  
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|Encapsule la **DATE** type de données utilisé dans OLE automation.|atlcomtime.h|  
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|Représente une heure relative, un intervalle de temps.|atlcomtime.h|  
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|Une classe similaire à Windows [POINT](../../mfc/reference/point-structure1.md) structure qui comprend également des fonctions de membre pour manipuler des `CPoint` et **POINT** structures.|atltypes.h|  
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|Une classe similaire à Windows [RECT](../../mfc/reference/rect-structure1.md) structure qui comprend également des fonctions de membre pour manipuler `CRect` objets et Windows `RECT` structures.|atltypes.h|  
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|Représente un `CSimpleStringT` objet.|atlsimpstr.h|  
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|Une classe similaire à la structure de la TAILLE de Windows, qui implémente une coordonnée relative ou une position.|atltypes.h|  
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|Fournit le nettoyage automatique des ressources des `GetBuffer` et `ReleaseBuffer` appelle un existant `CStringT` objet.|atlsimpstr.h|  
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|Représente les données d’un objet string.|atlsimpstr.h|  
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|Représente un `CStringT` objet.|atlstr.h CStringT.h (en fonction de MFC) (indépendante de MFC)|  
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|Représente une date et une heure absolue.|atltime.h|  
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|Un intervalle de temps, qui est stocké en interne en tant que le nombre de secondes dans l’intervalle de temps.|atltime.h|  
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|Représente l’interface pour un `CStringT` Gestionnaire de mémoire.|atlsimpstr.h|  
  
## <a name="see-also"></a>Voir aussi  
 [ATL et MFC des Classes partagées](../../atl-mfc-shared/atl-mfc-shared-classes.md)


