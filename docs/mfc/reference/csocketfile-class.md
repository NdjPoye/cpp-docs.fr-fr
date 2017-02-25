---
title: "CSocketFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSocketFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "archives [C++], réseau"
  - "CSocketFile class"
  - "networks [C++], archive"
  - "networks [C++], serializing to"
  - "sérialisation (C++), réseau"
  - "SOCKET handle"
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CSocketFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un objet d' `CFile` utilisé pour envoyer et recevoir des données sur un réseau via Windows Sockets.  
  
## Syntaxe  
  
```  
class CSocketFile : public CFile  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSocketFile::CSocketFile](../Topic/CSocketFile::CSocketFile.md)|Construit un objet `CSocketFile`.|  
  
## Notes  
 Vous pouvez lier l'objet d' `CSocketFile` à un objet d' `CSocket` à cet effet.  Vous pouvez également, et faites habituellement, liaison de l'objet d' `CSocketFile` à un objet d' `CArchive` pour simplifier l'émission et des données de recevoir à la sérialisation MFC.  
  
 Pour sérialiser \(envoyer\) de données, vous l'insérer dans l'archive, qui appelle les fonctions membres d' `CSocketFile` pour écrire des données dans l'objet d' `CSocket` .  Pour désérialiser \(recevoir\) de données, vous récupérez de l'archive.  Cela fait d'appeler l'archive des fonctions membres d' `CSocketFile` pour lire les données de l'objet d' `CSocket` .  
  
> [!TIP]
>  Outre l'utilisation `CSocketFile` comme décrit ici, vous pouvez l'utiliser comme fichier objet autonome, de même que vous pouvez à `CFile`, sa classe de base.  Vous pouvez également utiliser `CSocketFile` avec toutes les fonctions archive\- basées de sérialisation MFC.  Étant donné qu' `CSocketFile` ne prend pas en charge toutes les fonctionnalités d'`CFile`, la valeur par défaut MFC sérialisent des fonctions ne sont pas compatibles avec `CSocketFile`.  c'est particulièrement vrai de la classe d' `CEditView` .  Vous ne devez pas essayer de la sérialisation des données d' `CEditView` via un objet d' `CArchive` attaché à un objet d' `CSocketFile` à l'aide de `CEditView::SerializeRaw`; utilisation **CEditView::Serialize** à la place.  La fonction d' `SerializeRaw` s'attend à ce que le fichier objet a des fonctions, telles qu' `Seek`, qu' `CSocketFile` n'a pas.  
  
 Lorsque vous utilisez `CArchive` avec `CSocketFile` et `CSocket`, vous pouvez rencontrer une situation où **CSocket::Receive** écrit une boucle \(par **PumpMessages\(FD\_READ\)**\) attend la quantité demandée d'octets.  C'est parce que les Winsocks permettent un seul appel de recv par notification de FD\_READ, mais `CSocketFile` et `CSocket` permettent de plusieurs appels de recv par FD\_READ.  Si vous obtenez un FD\_READ lorsqu'il n'y a pas de données à lire, l'application s'arrête.  Si vous n'obtenez jamais un autre FD\_READ, l'application arrête de communiquer de socket.  
  
 Vous pouvez résoudre ce problème comme suit.  Dans la méthode d' `OnReceive` de votre classe de sockets, appelez **CAsyncSocket::IOCtl\(FIONREAD, ...\)** avant d'appeler la méthode d' `Serialize` de votre classe de message lorsque les données destinées à lire du socket dépassent la taille d'un à en\-tête pack TCP \(max communication Unit de la prise en charge de réseau, généralement au moins de 1096 octets\).  Si la taille des données disponibles est moins que nécessaire, attendez que les données à accepter puis démarrez que l'opération de lecture.  
  
 Dans l'exemple suivant, `m_dwExpected` est le nombre d'octets approximatif que l'utilisateur compte recevoir.  On suppose que vous le déclarez ailleurs dans votre code.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/CPP/csocketfile-class_1.cpp)]  
  
 Pour plus d'informations, consultez [Windows Sockets dans MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets : Utilisation des sockets avec des archives](../../mfc/windows-sockets-using-sockets-with-archives.md), ainsi que l' [API Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Fichier C](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## Configuration requise  
 **Header:** afxsock.h  
  
## Voir aussi  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket Class](../../mfc/reference/casyncsocket-class.md)   
 [CSocket Class](../../mfc/reference/csocket-class.md)