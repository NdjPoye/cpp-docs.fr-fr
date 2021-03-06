---
title: Classe de CSocketFile | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
dev_langs:
- C++
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e3bf8d9ee58143e7a96b85174e4533b3c2e50ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="csocketfile-class"></a>Classe de CSocketFile
Objet `CFile` utilisé pour envoyer et recevoir des données sur un réseau via Windows Sockets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSocketFile : public CFile  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSocketFile::CSocketFile](#csocketfile)|Construit un objet `CSocketFile`.|  
  
## <a name="remarks"></a>Notes  
 Vous pouvez attacher le `CSocketFile` de l’objet à un `CSocket` objet à cet effet. Vous pouvez également et généralement faire, d’attacher le `CSocketFile` de l’objet à un `CArchive` objet pour simplifier l’envoi et la réception des données à l’aide de la sérialisation MFC.  
  
 Pour sérialiser les données (envoi), insérez-le dans l’archive, qui appelle `CSocketFile` des fonctions membres pour écrire des données dans le `CSocket` objet. Pour désérialiser (réception), vous d’extraction des données à partir de l’archive. Cela entraîne l’archive à appeler `CSocketFile` des fonctions membres pour lire les données à partir de la `CSocket` objet.  
  
> [!TIP]
>  Outre l’utilisation de `CSocketFile` comme décrit ici, vous pouvez l’utiliser en tant qu’objet autonome, comme vous le faites avec `CFile`, sa classe de base. Vous pouvez également utiliser `CSocketFile` avec toutes les fonctions de sérialisation MFC basée sur une archive. Étant donné que `CSocketFile` ne prend pas en charge toutes les `CFile`sérialiser des fonctionnalités, certains MFC par défaut de fonctions ne sont pas compatibles avec `CSocketFile`. Cela est particulièrement vrai pour les `CEditView` classe. Vous ne devez pas essayer de sérialiser `CEditView` données via un `CArchive` objet attaché à un `CSocketFile` à l’aide de l’objet `CEditView::SerializeRaw`; utilisez **plutôt CEditView::Serialize** à la place. Le `SerializeRaw` fonction attend l’objet fichier ont des fonctions, telles que `Seek`, qui `CSocketFile` n’a pas.  
  
 Lorsque vous utilisez `CArchive` avec `CSocketFile` et `CSocket`, vous pouvez rencontrer une situation où **CSocket::Receive** entre dans une boucle (par **PumpMessages(FD_READ)**) en attente de la quantité d’octets. Il s’agit, car Windows sockets ne permettent qu’un seul appel reçus par la notification de FD_READ, mais `CSocketFile` et `CSocket` autoriser plusieurs appels reçus par FD_READ. Si vous obtenez un FD_READ lorsqu’il n’existe aucune donnée à lire, l’application se bloque. Si vous obtenez jamais FD_READ un autre, l’application cesse de communiquer via le socket.  
  
 Vous pouvez résoudre ce problème comme suit. Dans le `OnReceive` méthode de votre classe socket, appelez **CAsyncSocket::IOCtl (FIONREAD,...)**  avant d’appeler le `Serialize` méthode de votre classe de message lorsque les données attendues à lire à partir du socket dépassent la taille d’un paquet TCP (unité de transmission maximale de la moyenne de réseau, généralement au moins 1096 octets). Si la taille des données disponibles est inférieur au besoin, attendez que toutes les données à être reçu et ensuite seulement, démarrer l’opération de lecture.  
  
 Dans l’exemple suivant, `m_dwExpected` est le nombre approximatif d’octets que l’utilisateur s’attend à recevoir. Il est supposé que vous déclarez il ailleurs dans votre code.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]  
  
 Pour plus d’informations, consultez [Windows Sockets dans MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets : utilisation de Sockets avec des Archives](../../mfc/windows-sockets-using-sockets-with-archives.md), ainsi que [API Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxsock.h  
  
##  <a name="csocketfile"></a>  CSocketFile::CSocketFile  
 Construit un objet `CSocketFile`.  
  
```  
explicit CSocketFile(
    CSocket* pSocket,  
    BOOL bArchiveCompatible = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSocket`  
 Le socket à attacher à la `CSocketFile` objet.  
  
 `bArchiveCompatible`  
 Spécifie si l’objet de fichier doit être utilisé avec un `CArchive` objet. Passer **FALSE** uniquement si vous souhaitez utiliser le `CSocketFile` de l’objet de manière autonome comme vous le feriez autonome `CFile` objet, avec certaines limitations. Cet indicateur change la `CArchive` objet attaché à la `CSocketFile` objet gère sa mémoire tampon pour la lecture.  
  
### <a name="remarks"></a>Notes  
 Destructeur de l’objet dissocie lui-même à partir de l’objet socket lorsque l’objet est hors de portée ou est supprimé.  
  
> [!NOTE]
>  A `CSocketFile` peut également être utilisé comme un fichier (limité) sans un `CArchive` objet. Par défaut, le `CSocketFile` du constructeur `bArchiveCompatible` paramètre est **TRUE**. Spécifie que l’objet de fichier doit être utilisé avec une archive. Pour utiliser l’objet fichier sans archive, passez **FALSE** dans le `bArchiveCompatible` paramètre.  
  
 En mode « compatible archive », un `CSocketFile` objet offre de meilleures performances et réduit le risque de « blocage ». Un blocage se produit lorsque les sockets de transmission et de réception sont en attente sur l’autre, ou pour une ressource commune. Cette situation peut se produire si le `CArchive` objet travaillé avec la `CSocketFile` comme il le fait avec un `CFile` objet. Avec `CFile`, l’archive peut supposer que s’il reçoit le nombre d’octets qu’il a demandée, la fin du fichier a été atteinte.  
  
 Avec `CSocketFile`, toutefois, données message en fonction ; la mémoire tampon peut contenir plusieurs messages, donc recevoir moins que le nombre d’octets demandés n’implique pas la fin du fichier. L’application ne bloque pas, dans ce cas, ce qui est possible avec `CFile`, et poursuivre la lecture de messages à partir de la mémoire tampon jusqu'à ce que la mémoire tampon est vide. Le [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) fonction est utile pour surveiller l’état de la mémoire tampon de l’archive dans ce cas.  
  
 Pour plus d’informations sur l’utilisation de `CSocketFile`, consultez les articles [Windows Sockets : utilisation de Sockets avec des Archives](../../mfc/windows-sockets-using-sockets-with-archives.md) et [Windows Sockets : exemple de Sockets utilisant des Archives](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="see-also"></a>Voir aussi  
 [CFile (classe)](../../mfc/reference/cfile-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket (classe)](../../mfc/reference/casyncsocket-class.md)   
 [CSocket, classe](../../mfc/reference/csocket-class.md)
