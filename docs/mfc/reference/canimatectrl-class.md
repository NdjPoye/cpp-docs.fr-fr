---
title: "CAnimateCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimateCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "animation controls [C++], CAnimateCtrl class"
  - "CAnimateCtrl class"
  - "Windows common controls [C++], CAnimateCtrl class"
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimateCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités du contrôle animation communs windows.  
  
## Syntaxe  
  
```  
  
class CAnimateCtrl : public CWnd  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimateCtrl::CAnimateCtrl](../Topic/CAnimateCtrl::CAnimateCtrl.md)|Construit un objet `CAnimateCtrl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimateCtrl::Close](../Topic/CAnimateCtrl::Close.md)|Ferme un clip AVI.|  
|[CAnimateCtrl::Create](../Topic/CAnimateCtrl::Create.md)|Crée un contrôle animation et l'attache à un objet d' `CAnimateCtrl` .|  
|[CAnimateCtrl::CreateEx](../Topic/CAnimateCtrl::CreateEx.md)|Crée un contrôle animation avec les styles étendus par windows spécifiées et l'attache à un objet d' `CAnimateCtrl` .|  
|[CAnimateCtrl::IsPlaying](../Topic/CAnimateCtrl::IsPlaying.md)|Indique si un clip de \(AVI\) de format AVI lit.|  
|[CAnimateCtrl::Open](../Topic/CAnimateCtrl::Open.md)|Ouvre un clip AVI d'un fichier ou d'une ressource et affiche le premier frame.|  
|[CAnimateCtrl::Play](../Topic/CAnimateCtrl::Play.md)|Lit le clip AVI sans son.|  
|[CAnimateCtrl::Seek](../Topic/CAnimateCtrl::Seek.md)|Affiche un seul frame sélectionné du clip AVI.|  
|[CAnimateCtrl::Stop](../Topic/CAnimateCtrl::Stop.md)|Arrête de jouer un clip AVI.|  
  
## Notes  
 Ce contrôle \(et par conséquent la classe d' `CAnimateCtrl` \) est disponible uniquement aux programmes s'exécutant sous la version 3,51 de Windows 95, Windows 98, et Windows NT et versions ultérieures.  
  
 Un contrôle animation est une zone rectangulaire qui affiche un clip dans le format d'AVI \(format AVI\) de la vidéo et audio format standard de windows.  Un clip AVI est une série de trames bitmap, comme un film.  
  
 Les contrôles animation peuvent lire uniquement les clips AVI simples.  Spécifiquement, les clips à lire par un contrôle animation doivent répondre aux exigences suivantes :  
  
-   Il doit y avoir un seul flux vidéo et il doit avoir au moins un frame.  
  
-   Il peut y avoir au plus deux flux dans le fichier \(en général l'autre flux, le cas échéant, est un flux audio, bien que le contrôle animation ignore les informations audio\).  
  
-   Le clip doit être non compressé ou compressé avec la compression RLE8.  
  
-   Les espaces ne sont pas modification de la palette de flux vidéo.  
  
 Vous pouvez ajouter un clip AVI à votre application comme ressource AVI, ou elle peut accompagner votre application en tant que fichier AVI distinct.  
  
 Étant donné que votre thread continue de s'exécuter pendant que le clip AVI est affiché, une utilisation courante d'un contrôle animation est d'indiquer l'activité du système pendant une longue opération.  Par exemple, la boîte de dialogue recherche de l'Explorateur de fichiers affiche une loupe mobile comme recherches de système pour un fichier.  
  
 Si vous créez un objet d' `CAnimateCtrl` dans une boîte de dialogue ou d'une ressource de boîte de dialogue à l'aide de l'éditeur de boîtes de dialogue, il sera automatiquement détruit lorsque l'utilisateur ferme la boîte de dialogue.  
  
 Si vous créez un objet d' `CAnimateCtrl` dans une fenêtre, vous devrez peut\-être la destruction.  Si vous créez l'objet d' `CAnimateCtrl` sur la pile, elle est perdue automatiquement.  Si vous créez l'objet d' `CAnimateCtrl` sur le tas à l'aide de la fonction de **nouveau** , vous devez appeler **supprimer** sur l'objet pour le détruire.  Si vous dérivez une nouvelle classe d' `CAnimateCtrl` et allouez une mémoire dans cette classe hôte, substituez le destructeur d' `CAnimateCtrl` pour disposer les allocations.  
  
 Pour plus d'informations sur l'utilisation `CAnimateCtrl`, consultez [contrôles](../../mfc/controls-mfc.md) et l' [Utilisation CAnimateCtrl](../../mfc/using-canimatectrl.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](../Topic/CAnimateCtrl::Create.md)   
 [ON\_CONTROL](../Topic/ON_CONTROL.md)