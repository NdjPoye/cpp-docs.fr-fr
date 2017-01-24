---
title: "WSADATA, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WSADATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WSADATA (structure)"
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# WSADATA, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `WSADATA` permet de stocker les informations d'initialisation Windows Sockets retournées par un appel à la fonction globale `AfxSocketInit`.  
  
## Syntaxe  
  
```  
  
      struct WSAData {  
   WORD wVersion;  
   WORD wHighVersion;  
   char szDescription[WSADESCRIPTION_LEN+1];  
   char szSystemStatus[WSASYSSTATUS_LEN+1];  
   unsigned short iMaxSockets;  
   unsigned short iMaxUdpDg;  
   char FAR * lpVendorInfo;  
};  
```  
  
#### Paramètres  
 *wVersion*  
 La version de la spécification de Windows Sockets que la DLL de Windows Sockets s'attend à ce que l'appelant utilise.  
  
 *wHighVersion*  
 La version la plus récente de la spécification de Windows Sowkets que cette DLL peut prendre en charge \(également encodées comme ci\-dessus\).  Normalement, cela revient à **wVersion**.  
  
 *szDescription*.  
 Une chaîne ASCII terminée par le caractère NULL dans laquelle la DLL de Windows Sockets copie une description de l'implémentation de Windows Sockets, y compris l'ID de fournisseur.  Le texte \(jusqu'à 256 caractères de longueur\) peut contenir tous les caractères, mais fournisseurs sont prévenu contre l'inclusion de contrôles et de caractères de mise en forme : l'utilisation la plus probable qu'une application l'utilise est de l'afficher \(peut être de manière tronquée\) dans un message d'état.  
  
 *szSystemStatus*  
 ASCII une chaîne terminée par le caractère NULL dans laquelle la DLL de Windows Sockets copie des informations pertinentes sur l'état ou la configuration.  La DLL de Windows Sockets doit utiliser ce champ uniquement si les informations peuvent être utiles pour l'utilisateur ou l'équipe de support ; elle ne doit pas être considérée comme une extension du champ de **szDescription**.  
  
 *iMaxSockets*  
 Le nombre maximal de sockets qu'un seul processus peut potentiellement ouvrir.  Une implémentation Windows Sockets peut fournir un pool global de sockets pour l'allocation à tout processus ; sinon, elle peut allouer des ressources par processus aux sockets.  Le nombre peut ainsi réfléchir la façon dont la DLL de Windows Sockets ou le logiciel réseau a été configuré.  Les programmes d'écriture d'applications peuvent utiliser ce nombre comme une indication brute de si l'implémentation de Windows Sockets est utilisable par l'application.  Par exemple, un serveur X Windows peut activer **iMaxSockets** une fois le premier démarrage : si elle est inférieur à 8, l'application afficherait un message d'erreur instruisant l'utilisateur de reconfigurer le logiciel réseau. \(Il s'agit d'une situation dans laquelle le texte de **szSystemStatus** peut être utilisé.\) Évidemment rien ne garantit qu'une application spécifique peut allouer des sockets **iMaxSockets**, car il peut y avoir d'autres applications de Windows Sockets utilisée.  
  
 *iMaxUdpDg*  
 Taille en octets du plus grand datagramme de protocole utilisateur \(UDP\) qui peut être envoyés ou reçu par une application Windows Sockets.  Si l'implémentation n'impose aucune limite, **iMaxUdpDg** est zéro.  Dans la plupart des implémentations des sockets à Berkeley, il existe une limite implicite de 8192 octets sur les datagrammes UDP \(qui sont réduits en fragments si nécessaire\).  Une implémentation Windows Sockets peut imposer une limite basée, par exemple, sur l'allocation des tampons de réassemblage de fragment.  La valeur minimale de **iMaxUdpDg** pour une implémentation compatible Windows Sockets est 512.  Elle remarque que indépendamment de la valeur **iMaxUdpDg**, il est déconseillé de tenter d'envoyer un datagramme diffusé qui est plus grand que l'Unité de transmission maximale \(MTU\) du réseau. \(L'API Windows Sockets ne fournit pas de mécanisme permettant de déterminer la MTU, mais elle ne doit pas être inférieure à 512 octets.\)  
  
 *lpVendorInfo*  
 Un pointeur lointain vers une structure de données spécifique au fournisseur.  La définition de cette structure \(si disponible\) dépasse le cadre de la spécification de Windows Sockets.  
  
> [!NOTE]
>  Dans MFC, la structure `WSADATA` est retournée par la fonction `AfxSocketInit`, que vous appelez dans votre fonction `InitInstance`.  Vous pouvez récupérer la structure et l'enregistrer dans votre programme si vous devez en utiliser les informations plus tard.  
  
## Configuration requise  
 **En\-tête :** winsock2.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxSocketInit](../Topic/AfxSocketInit.md)