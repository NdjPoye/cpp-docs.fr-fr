---
title: "&#201;tapes dans une application cliente Internet classique | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications Internet, applications clientes"
  - "Internet (applications clientes), table générale"
  - "classes WinInet, programmation"
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# &#201;tapes dans une application cliente Internet classique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant montre les étapes que vous pouvez effectuer dans une application cliente Internet standard.  
  
|Votre objectif|Mesures que vous prenez|Effets|  
|--------------------|-----------------------------|------------|  
|Démarrez une session Internet.|Créez un objet métier de la classe [CInternetSession](../mfc/reference/cinternetsession-class.md)|Initialise WinInet et se connecte au serveur.|  
|Définissez une option de requête Internet \(limite de délai ou nombre de nouvelles tentatives, par exemple\).|Utilisez [CInternetSession::SetOption](../Topic/CInternetSession::SetOption.md).|Renvoie FALSE si l'opération a échoué.|  
|Créez une fonction de rappel pour vérifier l'état de la session.|Utilisez [CInternetSession::EnableStatusCallback](../Topic/CInternetSession::EnableStatusCallback.md).|Crée un rappel à [CInternetSession::OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md).  Remplacez `OnStatusCallback` pour créer votre propre routine de rappel.|  
|Connectez\-vous à un serveur Web, un serveur intranet, ou un fichier local.|Utilisez [CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md).|Analyse l'URL et ouvre une connexion au serveur spécifié.  Retourne [CStdioFile](../mfc/reference/cstdiofile-class.md) \(si vous passez un nom de fichier local à `OpenURL`\).  Il s'agit de l'objet grâce auquel vous accédez à des données récupérées à partir du serveur ou du fichier.|  
|Lire dans le fichier.|Utilisez [CInternetFile::Read](../Topic/CInternetFile::Read.md).|Lit le nombre d'octets spécifié avec une mémoire tampon que vous fournissez.|  
|Gestion des exceptions.|Utilisez la classe [CInternetException](../mfc/reference/cinternetexception-class.md).|Gère tous les types d'exception Internet communs.|  
|Arrête la session Internet.|Jetez l'objet [CInternetSession](../mfc/reference/cinternetsession-class.md).|Nettoie automatiquement les handles et les connexions de fichiers ouverts.|  
  
## Voir aussi  
 [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Composants requis pour les classes clientes Internet](../mfc/prerequisites-for-internet-client-classes.md)   
 [Écriture d'une application cliente Internet en utilisant des classes WinInet MFC](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)