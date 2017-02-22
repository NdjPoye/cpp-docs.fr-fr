---
title: "TN058&#160;: impl&#233;mentation de l&#39;&#233;tat du module MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.implementation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL (C++), états des modules"
  - "MFC (C++), gérer des données d'état"
  - "états des modules (C++), gérer des données d'état"
  - "états des modules (C++), basculer"
  - "état du processus (C++)"
  - "état du thread (C++)"
  - "TN058"
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# TN058&#160;: impl&#233;mentation de l&#39;&#233;tat du module MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Note technique qui décrit l'implémentation des éléments « état du module » MFC.  Une présentation de l'implémentation de l'état du module est essentielle pour l'utilisation des DLL partagées MFC d'une DLL \(ou du serveur OLE in\-process\).  
  
 Pour avoir lu cette remarque, reportez\-vous à « gérer les données d'état des modules de MFC » dans [Créer de nouveaux documents, windows, et vues](../mfc/creating-new-documents-windows-and-views.md).  Cet article contient des informations et des informations d'ordre général importantes d'utilisation de cette rubrique.  
  
## Vue d'ensemble  
 Il existe trois types d'informations d'état de MFC : État du module, état du processus, et l'état du thread.  Parfois ces types d'état peuvent être combinés.  Par exemple, les cartes du descripteur de MFC sont locaux du module et local de threads.  Cela permet à deux modules différents pour configurer des cartes dans chacune de leurs thread.  
  
 L'état et l'état du thread de processus sont similaires.  Les éléments de données sont des opérations qui sont traditionnellement été des variables globales, mais ont le besoin d'être spécifiques à un processus ou un thread fourni pour la prise en charge appropriée de Win32s ou pour la prise en charge multithread appropriée.  La catégorie un élément de données données tenant dans varie selon l'élément et sa sémantique souhaitée en ce qui concerne les limites de traitement et de threads.  
  
 L'état du module est unique car elle peut contenir l'état global ou réellement état qui est le local du processus ou des variables locales de threads.  En outre, il peut être rendu invisible rapidement.  
  
## Passer d'état du module  
 Chaque thread contient un pointeur vers « active » ou l'état du module active \(comme il y a une attente, le pointeur fait partie de l'état local du thread de MFC\).  Ce pointeur est modifié lorsque le thread de l'exécution passe une limite du module, telle qu'une application appelant avec un contrôle OLE ou DLL, ou un contrôle OLE appelant réimporter dans une application.  
  
 L'état du module en cours bascule en appelant **AfxSetModuleState**.  Dans la plupart des cas, vous allez traiter ne jamais directement l'API.  MFC, dans de nombreux cas, l'appelle automatiquement \(à WinMain, à OLE points d'entrée, à **AfxWndProc**, etc.\). Cette opération s'effectue dans n'importe quel composant que vous entrez pour lier statiquement dans **WndProc**spécial, et `WinMain` spécial \(ou\) qui `DllMain`connaît quel état du module doit être actif.  Vous pouvez voir ce code en consultant DLLMODUL.CPP ou APPMODUL.CPP dans le répertoire de MFC\\SRC.  
  
 Il est rare que vous souhaitez définir l'état du module et non le définir ensuite restaurée.  Le plus souvent vous souhaitez « push » votre propre état du module comme l'actif et ensuite, une fois que vous avez terminé, « fenêtre indépendante » en arrière d'origine de contexte.  Cette opération s'effectue par macro [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md) et la catégorie particulière **AFX\_MAINTAIN\_STATE**.  
  
 `CCmdTarget` a fonctionnalités spéciales pour basculer de prise en charge de l'état du module.  En particulier, `CCmdTarget` classe est la racine utilisée pour la OLE automation et les points d'entrée OLE COM.  Comme tout autre point d'entrée est système, ces points d'entrée doivent définir l'état du module.  Comment `CCmdTarget` donné sait\-il être ce que l'état du module « correct » doit ?  La réponse est que « retient » laquelle l'état du module « actif » lorsqu'il est construit, de sorte qu'il peut définir l'état du module en cours à celui valeur « retrouvée » lorsqu'elle est appelée par la suite.  Par conséquent, l'état du module avec lequel il associe un objet donné `CCmdTarget` est l'état du module qui était active lorsque l'objet a été construit.  Effectuez un exemple simple de chargement d'un serveur de INPROC, pour créer un objet, et d'appeler ses méthodes.  
  
1.  La DLL est chargé par OLE à **LoadLibrary**.  
  
2.  **RawDllMain** est appelée en premier.  Il définit l'état du module à l'état du module statique pour la DLL.  Pour cette raison **RawDllMain** est statiquement lié à la DLL.  
  
3.  Le constructeur de fabrique de la classe associée à notre objet est appelé.  `COleObjectFactory` est dérivé `CCmdTarget` par conséquent, il retient dans quel état du module son instancié.  Ceci est important — lorsque la classe de fabrique est appelée pour créer des objets, il sait maintenant quel état du module pour que le actuel.  
  
4.  `DllGetClassObject` est appelé pour obtenir la fabrique de la classe.  MFC recherche la liste de fabrique de la classe associée à ce module et le retourne.  
  
5.  **COleObjectFactory::XClassFactory2::CreateInstance** est appelé.  Avant de créer l'objet et le retourne, cette fonction définit l'état du module à l'état du module qui était active à l'étape 3 \(celui qui étaient actifs lorsque `COleObjectFactory` a été instancié\).  Cette opération s'effectue à l'intérieur de [METHOD\_PROLOGUE](../Topic/METHOD_PROLOGUE.md).  
  
6.  Lorsque l'objet est créé, il est aussi un dérivé et de la même manière `COleObjectFactory` de `CCmdTarget` retrouvés qui l'état du module est active, ainsi que le nouvel objet.  Maintenant l'objet qui savent état du module pour passer lorsqu'il est appelé.  
  
7.  Le client appelle une fonction sur le OLE objet COM qu'elle a reçu son appel de `CoCreateInstance`.  Lorsque l'objet est appelé il utilise `METHOD_PROLOGUE` pour basculer l'état du module comme `COleObjectFactory` faits.  
  
 Comme vous pouvez le voir, l'état du module est propagé de l'objet à l'objet lorsqu'ils sont créés.  Il est important d'effectuer définir l'état du module correctement.  S'il n'est pas définie, la DLL ou objet COM peut interagir mal à une application de MFC qui est appelant, ou il peut ne pas trouver les ressources propres, ou peut échouer d'autres méthodes malheureuses.  
  
 Notez que certains types de DLL, notamment les DLL « d'extension de MFC » ne basculent pas l'état du module dans leur **RawDllMain** \(en fait, elles ne sont généralement pas même **RawDllMain**\).  Cela est dû au fait qu'ils sont censés se comporter « comme si » il était effectivement présentes dans l'application qui les utilise.  Ils sont réellement de partie de l'application qui exécute et est leur intention de modification de l'état global de l'application.  
  
 Les contrôles OLE et d'autres DLL sont très différents.  Ils ne souhaitez pas modifier l'état de l'application appelant ; l'application qui est appelant ils même ne peut pas être une application de MFC et il peut être n'importe quelle condition à modifier.  C'est la raison pour laquelle afficher l'état du module a été inventé.  
  
 Pour les fonctions exportées à partir d'une DLL, telle qu'une qui affiche une boîte de dialogue dans la DLL, vous devez ajouter le code suivant au début de la fonction :  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 Cela permute l'état du module en cours avec l'état retourné par [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md) jusqu'à la fin de l'étendue actuelle.  
  
 Les problèmes avec des ressources dans les DLL se poseront si la macro `AFX_MODULE_STATE` n'est pas utilisée.  Par défaut, MFC utilise le handle de ressource d'application principale pour charger le modèle de ressources.  Ce modèle est réellement enregistré dans la DLL.  La cause première est que les informations d'état du module MFC n'ont pas été basculées par la macro `AFX_MODULE_STATE`.  Le handle de ressources est récupérée de l'état du module MFC.  Ne pas afficher l'état du module provoque l'utilisation du mauvais handle de ressource.  
  
 `AFX_MODULE_STATE` n'a pas besoin d'être placé dans chaque fonction de la DLL.  Par exemple, `InitInstance` peut être appelé par du code MFC dans l'application sans `AFX_MODULE_STATE` car MFC déplace automatiquement l'état du module avant `InitInstance` puis les le restaure après que `InitInstance` retourne.  Il en va de même pour tous les gestionnaires de table des messages.  Les DLL normaux ont en fait une procédure spéciale de base de données qui bascule automatiquement l'état du module avant d'acheminer un message.  
  
## Données locales de processus  
 Les données locales du processus ne sont pas concernées une telle importante préoccupation sans la demande de DLL de Win32s.  Dans Win32s toutes les DLL partagent les données agrégées, même lorsque chargé par plusieurs applications.  Il est très différent de « true » modèle de données de DLL Win32, où chaque DLL obtient une copie distincte de son espace de données dans chaque processus qui est attaché à la DLL.  Pour ajouter la complexité, les données allouée sur le segment dans une DLL de Win32s est en fait des détails du processus \(du moins dans la mesure où la propriété disparaît\).  Prenons le fragment de code suivant :  
  
```  
static CString strGlobal; // at file scope  
  
__declspec(dllexport)   
void SetGlobalString(LPCTSTR lpsz)  
{  
   strGlobal = lpsz;  
}  
  
__declspec(dllexport)  
void GetGlobalString(LPCTSTR lpsz, size_t cb)  
{  
   StringCbCopy(lpsz, cb, strGlobal);  
}  
```  
  
 Examinez ce qui se produit si le code ci\-dessus est en trouve dans une DLL et cette DLL est chargé par deux processus A et B \(il peut, en fait, à deux instances de la même application\).  Appels `SetGlobalString("Hello from A")`.  Par conséquent, la mémoire allouée pour les données `CString` dans le contexte du processus A.  N'oubliez pas que `CString` lui\-même est global et est visible par A et B.  Maintenant appels `GetGlobalString(sz, sizeof(sz))`de B.  B peut voir les données défini.  Cela est dû au fait que Win32s n'offre aucune protection entre les processus comme Win32 faits.  Il s'agit de la première problème ; dans de nombreux cas il n'est pas souhaitable de posséder des données globale de l'effet d'application qui est considérée pour appartenir à une autre application.  
  
 Il existe des problèmes supplémentaires.  Imaginons que A se ferme maintenant.  Lorsqu'Un se termine, la mémoire utilisée par la chaîne d''`strGlobal`' est disponible pour le système \- c. \- à\-d., toute la mémoire allouée par traitement est libérée automatiquement par le système d'exploitation.  Il n'est pas libérée car le destructeur de `CString` est appelé ; elle n'a pas encore été appelée.  Elle est libérée simplement parce que l'application qui l'a allouée fait partie de la scène.  Maintenant B s'appelait `GetGlobalString(sz, sizeof(sz))`, elle ne peut pas obtenir des données non valides.  Une application peut avoir utilisé la mémoire pour autre chose.  
  
 Il existe un problème.  MFC 3.x utilisaient une technique de stockage local de threads \(TLS\).  MFC 3.x allouerait un index de TLS qui en Win32s agit réellement en tant qu'index de stockage de processus LOCAL, bien qu'il n'est pas appelé que puis référencerait toutes les données selon l'index de TLS.  Cela s'apparente à l'index de TLS utilisé pour stocker les données de threads locales sur Win32 \(voir ci\-dessous pour plus d'informations sur cette rubrique.  Cela est fait en sorte que chaque DLL MFC au moins deux index de TLS par processus.  Lorsque vous pour charger plusieurs DLL de contrôle \(OLE OCXs\), vous n'avez pas rapidement de TLS \(seules disponibles à 64\).  En outre, MFC devait placer toutes ces données à un emplacement, dans une structure unique.  Il n'est pas très extensible et n'est pas idéale en ce qui concerne l'utilisation des index de TLS.  
  
 MFC 4.x adresse avec un jeu de modèles de la classe que vous pouvez « regrouper » dans les données qui doivent être des variables locales de processus.  Par exemple, le problème mentionné ci\-dessus peut être résolu en entrant :  
  
```  
struct CMyGlobalData : public CNoTrackObject  
{  
   CString strGlobal;  
};  
CProcessLocal<CMyGlobalData> globalData;  
  
__declspec(dllexport)   
void SetGlobalString(LPCTSTR lpsz)  
{  
   globalData->strGlobal = lpsz;  
}  
  
__declspec(dllexport)  
void GetGlobalString(LPCTSTR lpsz, size_t cb)  
{  
   StringCbCopy(lpsz, cb, globalData->strGlobal);  
}  
```  
  
 MFC implémente ce en deux étapes.  En premier lieu, il existe une couche sur les API Win32 **Tls\*** \(**TlsAlloc**, **TlsSetValue**, **TlsGetValue**, etc.\) qui utilisent uniquement deux index de TLS par processus, quel que soit le nombre de DLL vous avez.  Ensuite, le modèle `CProcessLocal` est fourni pour accéder à ces données.  Il remplace l'opérateur\> qui est ce qui permet la syntaxe intuitive qui s'affiche en haut.  Tous les objets qui sont inclus par `CProcessLocal` doivent être dérivés de `CNoTrackObject`.  `CNoTrackObject` fournit un allocateur de niveau inférieur \(**LocalAlloc**\/**LocalFree**\) et un destructeur virtuel tels que MFC peut automatiquement détruire les objets locaux de traitement lorsque le processus est terminé.  De tels objets peuvent avoir un destructeur personnalisé si le nettoyage supplémentaire est nécessaire.  L'exemple ci\-dessus ne nécessite pas de, puisque le compilateur génère un destructeur par défaut à détruire l'objet incorporé `CString`.  
  
 Il existe d'autres avantages intéressants à cette méthode.  Non seulement tous les objets `CProcessLocal` sont \-ils détruits automatiquement, elles ne sont pas construits tant qu'elles ne sont pas nécessaires.  `CProcessLocal::operator->` instanciera l'objet associé la première fois qu'elle est appelée, et aucun précédemment.  Dans l'exemple ci\-dessus, cela signifie que la chaîne d''`strGlobal`' ne sera pas construite que lors de la première **SetGlobalString** ou **GetGlobalString** est appelé.  Dans certains cas, cela peut permettre de réduire le temps de démarrage de la DLL.  
  
## Données local de threads  
 Semblable aux données locales de processus, données locales de threads est utilisé lorsque les données doivent être locales à un thread donné.  Autrement dit, vous avez besoin d'une instance distincte des données pour chaque thread qui contrôlent ces données.  Cela peut plusieurs fois être utilisé au lieu des mécanismes étendus de synchronisation.  Si les données ne doivent pas être partagée par plusieurs threads est, ces mécanismes peuvent être coûteux et inutiles.  Supposons que nous avons fait l'objet `CString` \(comme l'exemple ci\-dessus\).  Nous pouvons en faire local de threads en les encapsulant avec un modèle `CThreadLocal` :  
  
```  
struct CMyThreadData : public CNoTrackObject  
{  
   CString strThread;  
};  
CThreadLocal<CMyThreadData> threadData;  
  
void MakeRandomString()  
{  
   // a kind of card shuffle (not a great one)  
   CString& str = threadData->strThread;  
   str.Empty();  
   while (str.GetLength() != 52)  
   {  
      unsigned int randomNumber;  
      errno_t randErr;  
      randErr = rand_s( &randomNumber );  
      if ( randErr == 0 )  
      {  
         TCHAR ch = randomNumber % 52 + 1;  
         if (str.Find(ch) < 0)  
            str += ch; // not found, add it  
      }  
   }  
}  
```  
  
 Si `MakeRandomString` est appelé plusieurs threads différents, chacun « brouillerait » la chaîne de différentes façons sans nuire l'autre.  Cela est dû au fait qu'il y a en fait une instance `strThread` par thread au lieu de simplement une instance globale.  
  
 Remarque au lieu de la façon dont une référence est utilisée pour capturer l'adresse `CString` une fois qu'une fois pour chaque itération de la boucle.  Code de boucles ait été écrite avec `threadData->strThread` partout '`str`' est utilisé, mais il est beaucoup plus lentement dans l'exécution.  Il est préférable de mettre en cache une référence aux données lors de ces références se produisent dans des boucles for.  
  
 Le modèle de la classe `CThreadLocal` utilise les mêmes mécanismes que `CProcessLocal` faits et les mêmes techniques d'implémentation.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)