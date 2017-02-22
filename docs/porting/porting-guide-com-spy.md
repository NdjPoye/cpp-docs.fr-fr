---
title: "Guide du portage&#160;: COMSpy | Microsoft Docs"
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
ms.assetid: 24aa0d52-4014-4acb-8052-f4e2e4bbc3bb
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Guide du portage&#160;: COMSpy
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique est la deuxième d'une série d'articles qui décrit le processus de mise à niveau d'anciens projets Visual C\+\+ vers la dernière version de Visual Studio.  L'exemple de code utilisé dans cette rubrique a été compilé avec Visual Studio 2005.  
  
## COMSpy  
 COMSpy est un programme qui surveille et enregistre l'activité des composants de service sur un ordinateur.  Les composants de service sont des composants COM\+ qui s'exécutent sur un système et peuvent être utilisés par des ordinateurs du même réseau.  Ils sont gérés par la fonctionnalité Services de composants disponible dans le Panneau de configuration Windows.  
  
### Étape 1.Conversion du fichier projet  
 Le fichier projet a été rapidement converti, et le processus a généré un rapport de migration.  Certaines entrées du rapport signalent d'éventuels problèmes à résoudre.  Voici un problème qui a été signalé \(notez que, dans cette rubrique, nous avons parfois abrégé les messages d'erreur pour une meilleure lisibilité, par exemple, en supprimant les chemins d'accès complets\) :  
  
  **ComSpyAudit\\ComSpyAudit.vcproj: MSB8012: $\(TargetPath\) \('C:\\Users\\UserName\\Desktop\\spy\\spy\\ComSpyAudit\\.  \\XP32\_DEBUG\\ComSpyAudit.dll'\) does not match the Librarian's OutputFile property value '.  \\XP32\_DEBUG\\ComSpyAudit.dll' \('C:\\Users\\UserName\\Desktop\\spy\\spy\\XP32\_DEBUG\\ComSpyAudit.dll'\) in project configuration 'Unicode Debug&#124;Win32'.  This may cause your project to build incorrectly.  To correct this, please make sure that $\(TargetPath\) property value matches the value specified in %\(Lib.OutputFile\).**  Un des problèmes fréquents durant la mise à niveau des projets est causé par le paramètre OutputFile de l'éditeur de liens qui n'est pas correctement défini dans la boîte de dialogue des propriétés de projet. Le cas échéant, ce paramètre doit être modifié.  Pour les projets créés dans une version antérieure à Visual Studio 2010, le paramètre OutputFile, quand il n'a pas une valeur standard, n'est pas toujours reconnu par l'Assistant Conversion automatique.  Dans cet exemple, les chemins d'accès des fichiers de sortie ont été définis sur un dossier non standard, XP32\_DEBUG.  Pour en savoir plus sur cette erreur, nous avons consulté un [billet de blog](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx) traitant de la mise à niveau des projets Visual C\+\+ 2010. Cette mise à niveau a introduit un changement majeur, à savoir le remplacement de vcbuild par msbuild.  D'après ce blog, la valeur par défaut du paramètre OutputFile à la création d'un projet est $\(OutDir\)$\(TargetName\)$\(TargetExt\). Cette valeur n'est pas définie au moment de la conversion et il n'est donc pas possible de vérifier si la valeur est correcte dans les projets convertis.  Essayons toutefois d'utiliser cette valeur pour le paramètre OutputFile et voyons si elle est acceptée.  Cela ne pose pas de problème. Nous pouvons donc continuer.  S'il n'y a pas de raison particulière justifiant l'utilisation d'un dossier de sortie non standard, nous vous recommandons d'utiliser l'emplacement standard.  Dans cet exemple, nous avions choisi de conserver l'emplacement de sortie non standard pour le processus de portage et de mise à niveau. "$\(OutDir\)" a été résolu en dossier XP32\_DEBUG dans la configuration Debug et en dossier ReleaseU dans la configuration Release.  
  
### Étape 2.Préparation de la build  
 Le processus de build du projet porté a généré un certain nombre d'erreurs et d'avertissements.  
  
 ComSpyCtl n'a pas pu être compilé en raison de cette erreur du compilateur :  
  
  **atlcom.h\(611\): error C2664: 'HRESULT CComSpy::IPersistStreamInit\_Save\(LPSTREAM,BOOL,ATL::ATL\_PROPMAP\_ENTRY \*\)': cannot convert argument 3 from 'const ATL::ATL\_PROPMAP\_ENTRY \*' to 'ATL::ATL\_PROPMAP\_ENTRY \*'**  
**atlcom.h\(611\): note: Conversion loses qualifiers**  
**atlcom.h\(608\): note: while compiling class template member function 'HRESULT ATL::IPersistStreamInitImpl\<CComSpy\>::Save\(LPSTREAM,BOOL\)'**  
**\\spy\\spy\\comspyctl\\ccomspy.h\(28\): note: see reference to class template instantiation 'ATL::IPersistStreamInitImpl\<CComSpy\>' being compiled** L'erreur fait référence à la méthode Save sur la classe IPersistStreamInitImpl dans le fichier atlcom.h.  
  
```  
STDMETHOD(Save)(_Inout_ LPSTREAM pStm, _In_ BOOL fClearDirty)  
{  
T* pT = static_cast<T*>(this);  
ATLTRACE(atlTraceCOM, 2, _T("IPersistStreamInitImpl::Save\n"));  
return pT->IPersistStreamInit_Save(pStm, fClearDirty, T::GetPropertyMap());  
}  
```  
  
 Le problème est qu'une conversion qui était acceptée par une ancienne version du compilateur n'est plus valide.  Pour être conforme à la norme C\+\+, du code qui était auparavant accepté ne l'est plus.  Dans ce cas, passer un pointeur non const à une fonction qui attend un pointeur const n'est pas une méthode sûre.  La solution consiste à trouver la déclaration de IPersistStreamInit\_Save sur la classe CComSpy et ajouter le modificateur const au troisième paramètre.  
  
```  
HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM pStm, BOOL /* fClearDirty */, const ATL_PROPMAP_ENTRY* pMap)  
  
```  
  
 Modifiez également IPersistStreamInit\_Load de façon similaire.  
  
```  
HRESULT IPersistStreamInit_Load(LPSTREAM pStm, const ATL_PROPMAP_ENTRY* pMap);  
```  
  
 L'erreur suivante concerne l'inscription.  
  
  **error MSB3073: The command "regsvr32 \/s \/c "C:\\Users\\username\\Desktop\\spy\\spy\\ComSpyCtl\\.  \\XP32\_DEBUG\\ComSpyCtl.lib"**  
**error MSB3073: echo regsvr32 exec.  time \> ".  \\XP32\_DEBUG\\regsvr32.trg"**  
**error MSB3073:**  
**error MSB3073: :VCEnd" exited with code 3.**  Nous n'avons plus besoin de cette commande d'inscription post\-build.  Au lieu de cela, nous supprimons simplement la commande de build personnalisée et nous définissons les paramètres de l'éditeur de liens pour inscrire la sortie.  
  
### Traitement des avertissements  
 Le projet génère l'avertissement d'éditeur de liens suivant.  
  
  **warning LNK4075: ignoring '\/EDITANDCONTINUE' due to '\/SAFESEH' specification** L'option de compilateur \/SAFESEH n'est pas utile en mode debug, contrairement à l'option \/EDITANDCONTINUE. La solution consiste donc à désactiver \/SAFESEH pour les configurations Debug uniquement.  Pour faire cela, nous ouvrons la boîte de dialogue Propriétés du projet qui génère cette erreur. Ensuite, nous définissons le paramètre Configuration sur Debug \(en fait, Debug Unicode\), puis dans la section Avancé de l'éditeur de liens, nous rétablissons la propriété Image avec gestionnaires d'exceptions sécurisés sur Non \(\/SAFESEH:NO\).  
  
 Le compilateur nous avertit que PROP\_ENTRY\_EX est déconseillée.  Elle n'est pas sécurisée et doit être remplacée par PROP\_ENTRY\_TYPE\_EX.  
  
```  
BEGIN_PROPERTY_MAP(CComSpy)  
PROP_ENTRY_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_ENTRY_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_ENTRY_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_ENTRY_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy)  
PROP_PAGE(CLSID_StockFontPage)  
END_PROPERTY_MAP()  
```  
  
 Nous modifions le code dans ccomspy.h en conséquence, en ajoutant les types COM appropriés.  
  
```  
BEGIN_PROPERTY_MAP(CComSpy)  
PROP_ENTRY_TYPE_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy, VT_BSTR)  
PROP_ENTRY_TYPE_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)  
PROP_ENTRY_TYPE_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)  
PROP_ENTRY_TYPE_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy, VT_UINT)  
PROP_PAGE(CLSID_StockFontPage)  
END_PROPERTY_MAP()  
```  
  
 Nous arrivons aux derniers avertissements à traiter, qui sont également dus aux vérifications de conformité plus strictes du compilateur :  
  
  **\\spy\\comspyctl\\usersub.h\(70\): warning C4457: declaration of 'var' hides function parameter**  
**\\spy\\comspyctl\\usersub.h\(48\): note: see declaration of 'var'**  
**\\spy\\comspyctl\\usersub.h\(94\): warning C4018: '\<': signed\/unsigned mismatch**  
 **ComSpy.cpp**  
**\\spy\\comspyctl\\comspy.cpp\(186\): warning C4457: declaration of 'bHandled' hides function parameter**  
**\\spy\\spy\\comspyctl\\comspy.cpp\(177\): note: see declaration of 'bHandled'** L'avertissement C4018 provient de ce code :  
  
```  
for (i=0;i<lCount;i++)  
    CoTaskMemFree(pKeys[i]);  
```  
  
 Le problème est que i est déclaré comme UINT et lCount est déclaré en tant que type long, d'où l'incompatibilité signed\/unsigned.  Ce ne serait pas pratique de changer le type de lCount en UINT, dans la mesure où il obtient sa valeur de IMtsEventInfo::get\_Count, qui utilise le type long et qui n'est pas dans le code utilisateur.  Nous préférons ajouter un cast dans le code.  Un cast C\-style serait possible pour un cast numérique comme celui\-ci, mais static\_cast est le style recommandé.  
  
```  
for (i=0;i<static_cast<UINT>(lCount);i++)  
    CoTaskMemFree(pKeys[i]);  
```  
  
 Ces avertissements ont été générés parce qu'une variable a été déclarée dans une fonction contenant un paramètre avec le même nom, ce qui peut potentiellement induire une confusion dans le code.  Nous avons résolu ce problème en modifiant les noms des variables locales.  
  
```  
  
```  
  
### Étape 3.Test et débogage  
 Nous avons testé l'application d'abord en exécutant les différents menus et commandes, puis en fermant l'application.  Le seul problème signalé était une assertion de débogage à la fermeture de l'application.  Le problème est survenu dans le destructeur de CWindowImpl, une classe de base de l'objet CSpyCon, composant COM principal de l'application.  L'échec d'assertion s'est produit dans le code suivant dans atlwin.h.  
  
```  
virtual ~CWindowImplRoot()  
{  
#ifdef _DEBUG  
if(m_hWnd != NULL)// should be cleared in WindowProc  
{  
ATLTRACE(atlTraceWindowing, 0, _T("ERROR - Object deleted before window was destroyed\n"));  
ATLASSERT(FALSE);  
}  
#endif //_DEBUG  
}  
```  
  
 hWnd est normalement défini à zéro dans la fonction WindowProc, mais cela n'a pas été le cas. Au lieu du WindowProc par défaut, un gestionnaire personnalisé a été appelé pour le message Windows \(WM\_SYSCOMMAND\) qui ferme la fenêtre.  Dans le gestionnaire personnalisé, hWnd n'était pas défini à zéro.  Examinons un code similaire dans la classe CWnd de MFC. Nous voyons que la suppression d'une fenêtre entraîne un appel à OnNcDestroy. Dans MFC, la documentation recommande d'appeler le NcDestroy de base lors de la substitution de CWnd::OnNcDestroy. Cela permet de vous assurer que les opérations de nettoyage requises sont effectuées, y compris la séparation du handle de la fenêtre ou, en d'autres termes, la définition de hWnd à zéro.  Cette assertion aurait pu aussi être déclenchée dans la version initiale de l'exemple, car le même code d'assertion était présent dans l'ancienne version de atlwin.h.  
  
 Pour tester la fonctionnalité de l'application, nous avons créé un composant de service à l'aide du modèle de projet ATL, et choisi d'ajouter la prise en charge de COM\+ dans l'Assistant Projet ATL.  Si vous n'avez pas encore utilisé de composants de service, vous pouvez facilement en créer un, l'inscrire et le rendre disponible sur le système ou le réseau pour d'autres applications.  L'application COMSpy est conçue pour surveiller l'activité des composants de service et servir ainsi d'aide au diagnostic.  
  
 Nous avons ensuite ajouté une classe, choisi un objet ATL et spécifié le nom de l'objet \(Dog\)   Puis, dans dog.h et dog.cpp, nous avons ajouté l'implémentation.  
  
```  
STDMETHODIMP CDog::Wag(LONG* lDuration)  
{  
    // TODO: Add your implementation code here  
    *lDuration = 100l;  
    return S_OK;  
}  
```  
  
 Ensuite, nous l'avons généré et inscrit \(vous devez exécuter Visual Studio en tant qu'administrateur\), et nous l'avons activé à l'aide de l'application Composants de service dans le Panneau de configuration Windows.  Nous avons créé un projet Windows Forms C\#, fait glisser un bouton sur le formulaire à partir de la boîte à outils et double\-cliqué sur un gestionnaire d'événements Click.  Nous avons ajouté le code suivant pour instancier le composant Dog.  
  
```  
private void button1_Click(object sender, EventArgs e)  
{  
    ATLProjectLib.Dog dog1 = new ATLProjectLib.Dog();  
    dog1.Wag();  
}  
```  
  
 Cela a été exécuté sans problème. Avec COMSpy installé, exécuté et configuré pour surveiller le composant Dog, un grand nombre d'informations sur l'activité s'affichent.  
  
## Voir aussi  
 [Portage et mise à niveau : exemples et études de cas](../porting/porting-and-upgrading-examples-and-case-studies.md)   
 [Exemple suivant : Spy \+\+](../porting/porting-guide-spy-increment.md)   
 [Exemple précédent : Scribble MFC](../porting/porting-guide-mfc-scribble.md)