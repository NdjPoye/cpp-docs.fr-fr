---
title: "CWaitCursor Class | Microsoft Docs"
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
  - "CWaitCursor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "curseurs, wait cursor"
  - "CWaitCursor class"
  - "wait cursors"
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWaitCursor Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet d'un\- ligne d'afficher un curseur d'attente, qui est généralement affichée comme un sablier, alors que vous effectuez une longue opération.  
  
## Syntaxe  
  
```  
class CWaitCursor  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWaitCursor::CWaitCursor](../Topic/CWaitCursor::CWaitCursor.md)|Construit un objet d' `CWaitCursor` et affiche le curseur d'attente.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWaitCursor::Restore](../Topic/CWaitCursor::Restore.md)|Restaure le curseur d'attente après qu'il a été modifié.|  
  
## Notes  
 `CWaitCursor` n'a pas de classe de base.  
  
 Les bonnes fenêtres programmation des méthodes requièrent que vous affichez un curseur d'attente chaque fois que vous exécutez une opération qui prend beaucoup de temps.  
  
 Pour afficher un curseur d'attente, définissez uniquement une variable d' `CWaitCursor` avant le code qui exécute une longue opération.  Le constructeur de l'objet entraîne automatiquement le curseur d'attente à afficher.  
  
 Lorsque l'objet est hors de portée \(à la fin de le bloc dans lequel l'objet d' `CWaitCursor` est déclaré\), son destructeur place le curseur au curseur précédent.  En d'autres termes, l'objet exécute un nettoyage nécessaire automatiquement.  
  
> [!NOTE]
>  En raison de la façon dont leurs constructeurs et les destructeurs, les objets d' `CWaitCursor` sont toujours déclarés en tant que variables locales \(ils ne sont jamais déclarés comme variables globales sont ni ils ont alloué avec **nouveau**.  
  
 Si vous exécutez une opération qui peut provoquer le curseur d'être modifiée, comme afficher un message ou une boîte de dialogue, appelez la fonction membre de [Restaurer](../Topic/CWaitCursor::Restore.md) pour restaurer le curseur d'attente.  Il est correct d'appeler **Restaurer** même lorsqu'un curseur d'attente est actuellement affiché.  
  
 Une autre façon d'afficher un curseur d'attente est d'utiliser la combinaison de [CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md), de [CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md), et éventuellement de [CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md).  Toutefois, il est plus facile à utiliser `CWaitCursor` parce que vous n'avez pas besoin de définir le curseur vers le curseur précédent lorsque vous avez terminé avec une longue opération.  
  
> [!NOTE]
>  MFC définit et restaure le curseur à l'aide de la fonction virtuelle de [CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md) .  Vous pouvez substituer cette fonction pour fournir un comportement personnalisé.  
  
## Hiérarchie d'héritage  
 `CWaitCursor`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Exemple  
 [!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/CPP/cwaitcursor-class_1.cpp)]  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md)   
 [CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md)   
 [CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md)   
 [CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md)   
 [Comment faire : Modifiez le curseur de la souris dans une application Microsoft Foundation Class ?](http://go.microsoft.com/fwlink/?LinkID=128044)