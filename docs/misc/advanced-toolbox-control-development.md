---
title: "D&#233;veloppement avanc&#233; de contr&#244;les de bo&#238;te &#224; outils | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Boîte à outils (Kit de développement logiciel Visual Studio SDK), ajout d’éléments à l’aide de MPF (Managed Package Framework)"
ms.assetid: d22479a8-6d95-400c-a115-f46d10c10d2f
caps.latest.revision: 19
caps.handback.revision: 19
manager: "douge"
---
# D&#233;veloppement avanc&#233; de contr&#244;les de bo&#238;te &#224; outils
> [!NOTE]
>  La méthode recommandée pour ajouter des contrôles personnalisés à la boîte à outils est d'utiliser des modèles de contrôle de la boîte à outils fournis avec Visual Studio 10 SDK.  Cette rubrique est conservé pour la compatibilité descendante, pour ajouter des contrôles existants à la boîte à outils, et pour le développement avancées de contrôle de la boîte à outils.  
>   
>  Pour plus d'informations sur la création de contrôles de boîte à outils en utilisant des modèles, consultez [Comment : créer un contrôle de boîte à outils qui utilise Windows Forms](../misc/how-to-create-a-toolbox-control-that-uses-windows-forms.md) et le [Création d’un contrôle de boîte à outils WPF](../Topic/Creating%20a%20WPF%20Toolbox%20Control.md).  
  
 Un VSPackage en fonction de managed package peut étendre les fonctionnalités de boîte à outils de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] en ajoutant des contrôles, des objets dérivés des objets d' <xref:System.Drawing.Design.ToolboxItem> .  chaque <xref:System.Drawing.Design.ToolboxItem> est implémenté par un objet dérivé d' <xref:System.ComponentModel.Component>.  
  
## fournisseur VSPackage d'élément de boîte à outils  
 Un VSPackage en fonction de managed package doit stocker comme un fournisseur de contrôle de boîte à outils via des attributs de [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] et des événements Boîte à outils\-mis en relation par handle.  
  
#### Pour configurer un VSPackage en tant que fournisseur d'élément de boîte à outils  
  
1.  créez une instance d' <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> appliqué à la classe implémentant <xref:Microsoft.VisualStudio.Shell.Package>.  Par exemple :  
  
    ```vb#  
    Namespace Vsip.LoadToolboxMembers   
        <ProvideToolboxItems(14)> _   
        <DefaultRegistryRoot("Software\Microsoft\VisualStudio\8.0")> _   
        <InstalledProductRegistration(False, "#100", "#102", "1.0", IconResourceID := 400)> _   
        <ProvideLoadKey("Standard", "1.0", "Package Name", "Company", 1)> _   
        <ProvideMenuResource(1000, 1)> _   
        <Guid("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")> _   
        Public Class LoadToolboxMembers   
            Inherits Package   
        End Class   
    End Namespace  
    ```  
  
    ```c#  
    namespace Vsip.LoadToolboxMembers {  
        [ProvideToolboxItems(14)]  
        [DefaultRegistryRoot("Software\\Microsoft\\VisualStudio\\8.0")]  
        [InstalledProductRegistration(false, "#100", "#102", "1.0", IconResourceID = 400)]  
        [ProvideLoadKey("Standard", "1.0", "Package Name", "Company", 1)]  
        [ProvideMenuResource(1000, 1)]  
        [Guid("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")]  
        public class LoadToolboxMembers : Package {  
    ```  
  
    > [!NOTE]
    >  le constructeur pour <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> prend un numéro de version entier comme argument.  l'environnement de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] utilise ce numéro de version pour déterminer si un VSPackage fournissant des objets d' <xref:System.Drawing.Design.ToolboxItem> doit être rechargé ou si les informations mises en cache peuvent être utilisées par la boîte à outils.  Pour garantir recharger d'un VSPackage en fournissant <xref:System.Drawing.Design.ToolboxItem> qui est en cours de développement, incrémentez toujours ce numéro de version après toute modification.  
  
2.  Si les objets d' <xref:System.Drawing.Design.ToolboxItem> fournissent des formats de presse\-papiers non de boîte à outils standard, une instance d' <xref:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute> doit être appliquée à la classe implémentant l'objet d' <xref:Microsoft.VisualStudio.Shell.Package> pour chaque format de presse\-papiers pris en charge par les objets d' <xref:System.Drawing.Design.ToolboxItem> que le VSPackage fournit.  
  
     Pour plus d'informations sur les formats de presse\-papiers pris en charge par la boîte à outils, consultez [Extension de la boîte à outils](../misc/extending-the-toolbox.md).  
  
    > [!NOTE]
    >  Si un VSPackage indique qu'il fournit à tous les objets d' <xref:System.Drawing.Design.ToolboxItem> les formats de presse\-papiers non standard, l'environnement de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] suppose que seules ces formats indiqués par les instances d' <xref:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute> appliquées à l'implémentation de classe d'<xref:Microsoft.VisualStudio.Shell.Package> d'un VSPackage sont pris en charge par le VSPackage.  Si un VSPackage doit prendre en charge les formats de presse\-papiers par défaut ainsi qu'un format non standard, il doit implémenter une instance d' <xref:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute> pour chaque format par défaut ainsi que le format non standard.  
  
3.  Si le VSPackage fournit la possibilité de configuration dynamique d' <xref:System.Drawing.Design.ToolboxItem>, il doit :  
  
    1.  Appliquez une instance d' <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute> a généré en utilisant <xref:System.Type> que le package utilise pour implémenter l'interface de <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> .  
  
    2.  Sur une indépendante de classe d' `public` d' <xref:Microsoft.VisualStudio.Shell.Package>du VSPackage, le VSPackage doit implémenter l'interface d' <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> .  
  
         Une instance d' <xref:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute> doit être appliquée à la classe implémentant <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem>, à l'aide d'une chaîne contenant les critères d'une sélection \(filtre\) en tant qu'argument au constructeur de l'instance d' <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute> .  
  
 Pour plus d'informations sur la façon de signaler à l'environnement de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] qu'un VSPackage fournit les contrôles de boîte à outils, consultez [Inscription des fonctionnalités de prise en charge de boîte à outils](../misc/registering-toolbox-support-features.md).  
  
 Pour obtenir un exemple illustrant comment il peut implémenter la prise en charge d' <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> , consultez [Procédure pas à pas : personnalisation dynamique de la configuration des éléments de la boîte à outils](../misc/walkthrough-customizing-toolbox-item-configuration-dynamically.md).  
  
1.  VSPackages fournissant <xref:System.Drawing.Design.ToolboxItem> doit gérer <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> les événements et d' <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> .  
  
    1.  implémentez les gestionnaires pour les événements d' <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> et d' <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> :  
  
        ```vb#  
        Private Sub OnToolboxUpgraded(ByVal sender As Object, ByVal e As EventArgs)   
            OnToolboxInitialized(send, e)   
        End Sub   
        Private Sub OnToolboxInitialized(ByVal sender As Object, ByVal e As EventArgs)   
            'Make sure all toolbox items are added.   
        End Sub  
        ```  
  
        ```c#  
        private void OnToolboxUpgraded(object sender, EventArgs e) {  
            OnToolboxInitialized(send,e);  
        }  
        private void OnToolboxInitialized(object sender, EventArgs e) {  
            //Make sure all toolbox items are added.  
        }  
        ```  
  
    2.  Abonnez \-vous aux événements d' <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> et d' <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> .  
  
         Cela est généralement fait dans la méthode d' <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> de l'implémentation d' <xref:Microsoft.VisualStudio.Shell.Package> :  
  
        ```vb#  
        Protected Overloads Overrides Sub Initialize()   
            AddHandler ToolboxInitialized, AddressOf OnToolboxInitialized   
            AddHandler ToolboxUpgraded, AddressOf OnToolboxUpgraded   
        End Sub  
        ```  
  
        ```c#  
        protected override void Initialize() {  
            ToolboxInitialized += new EventHandler(OnToolboxInitialized);  
            ToolboxUpgraded += new EventHandler(OnToolboxUpgraded);  
        }  
        ```  
  
     Pour obtenir un exemple d'implémentation des gestionnaires pour <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> les événements et d' <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> , consultez [Procédure pas à pas : chargement automatique d’éléments de boîte à outils](../misc/walkthrough-autoloading-toolbox-items.md).  
  
## Conception du contrôle de boîte à outils  
 L'implémentation sous\-jacente d'un contrôle de boîte à outils doit être dérivée d' <xref:System.ComponentModel.Component> et être encapsulé dans la valeur par défaut ou une implémentation de l'objet dérivé d' <xref:System.Drawing.Design.ToolboxItem> .  
  
 La façon la plus facile de fournir <xref:System.ComponentModel.Component>\- l'implémentation dérivée les contrôles de boîte à outils est en étendant un objet dérivé d' <xref:System.Windows.Forms.Control>, en particulier, la classe d' <xref:System.Windows.Forms.UserControl> .  
  
#### Pour créer les contrôles de boîte à outils  
  
1.  Utilisez la commande pour **Ajouter un nouvel élément** De l'Explorateur de Solutions de créer un objet de boîte à outils qui implémente <xref:System.Windows.Forms.UserControl>.  
  
    ```vb#  
    Public Partial Class ToolboxControl1   
        Inherits UserControl   
        Public Sub New()   
            InitializeComponent()   
        End Sub   
        Private Sub button1_Click(ByVal sender As Object, ByVal e As EventArgs)   
            MsgBox("Hello world from" & Me.ToString())   
        End Sub   
  
        Private Sub ToolboxItem1_Load(ByVal sender As Object, ByVal e As EventArgs)   
  
        End Sub   
    End Class  
    ```  
  
    ```c#  
    public partial class ToolboxControl1 : UserControl {  
            public ToolboxControl1() {  
                InitializeComponent();  
            }  
  
            private void button1_Click(object sender, EventArgs e) {  
                MessageBox.Show("Hello world from" + this.ToString());  
            }  
  
            private void ToolboxItem1_Load(object sender, EventArgs e) {  
  
            }  
        }  
    ```  
  
     Pour plus d'informations sur la création de contrôles Windows Forms et les contrôles de boîte à outils, consultez [Développement de contrôles Windows Forms personnalisés avec le .NET Framework](../Topic/Developing%20Custom%20Windows%20Forms%20Controls%20with%20the%20.NET%20Framework.md) ou le [Procédure pas à pas : chargement automatique d’éléments de boîte à outils](../misc/walkthrough-autoloading-toolbox-items.md).  
  
2.  \(Facultatif\) une application peut choisir d'utiliser un objet personnalisé dérivé de l'objet d' <xref:System.Drawing.Design.ToolboxItem> fournisse son contrôle de boîte à outils à **boîte à outils**.  
  
    > [!NOTE]
    >  Toute classe dérivée de l'objet d' <xref:System.Drawing.Design.ToolboxItem> doit avoir une instance d' <xref:System.SerializableAttribute> appliqué à celui\-ci.  
  
     Une implémentation personnalisée dérivée d' <xref:System.Drawing.Design.ToolboxItem> peut étendre une application en fournissant un meilleur contrôle de la façon dont les données d' <xref:System.Drawing.Design.ToolboxItem> est sérialisée, une gestion comprendre les métadonnées de concepteur, une prise en charge pour les formats de presse\-papiers non standard, et une fonctionnalité qui permet l'interaction utilisateur.  
  
     Dans l'exemple, les utilisateurs sont appelés par une boîte de dialogue à sélectionner les fonctions :  
  
    ```vb#  
    <ToolboxItemAttribute(GetType(CustomControl))> _   
    <Serializable()> _   
    Class CustomControl   
        Inherits ToolboxItem   
  
        Public Sub New(ByVal type As Type)   
            MyBase.New(GetType(CustomControl))   
        End Sub   
        Public Sub New(ByVal type As Type, ByVal icon As Bitmap)   
            MyBase.New(GetType(SCustomControl))   
            Me.DisplayName = "CustomContorl"   
            Me.Bitmap = icon   
        End Sub   
  
        Private Sub New(ByVal info As SerializationInfo, ByVal context As StreamingContext)   
            Deserialize(info, context)   
        End Sub   
        Protected Overloads Overrides Function CreateComponentsCore(ByVal host As IDesignerHost) As IComponent()   
            Dim dialog As New CustomControlDialog(host)   
            Dim dialogResult__1 As DialogResult = dialog.ShowDialog()   
            If dialogResult__1 = DialogResult.OK Then   
                Dim component As IComponent = DirectCast(dialog.CustomInstance, IComponent)   
                Dim container As IContainer = host.Container   
                container.Add(component)   
                Return New IComponent() {component}   
            Else   
                Return New IComponent() {}   
            End If   
        End Function   
    End Class  
    ```  
  
    ```c#  
    [ToolboxItemAttribute(typeof(CustomControl))]  
    [Serializable]  
    class CustomControl : ToolboxItem {  
  
        public CustomControl(Type type) : base(typeof(CustomControl)) {}  
            public CustomControl(Type type, Bitmap icon) : base(typeof(SCustomControl)) {  
            this.DisplayName = "CustomContorl";  
            this.Bitmap = icon;  
        }  
  
        private CustomControl(SerializationInfo info, StreamingContext context) {  
            Deserialize(info, context);  
        }  
        protected override IComponent[] CreateComponentsCore(IDesignerHost host) {  
            CustomControlDialog dialog = new CustomControlDialog(host);  
            DialogResult dialogResult = dialog.ShowDialog();  
            if (dialogResult == DialogResult.OK) {  
                IComponent component = (IComponent)dialog.CustomInstance;  
                IContainer container = host.Container;  
                container.Add(component);  
                return new IComponent[] { component };  
            }  
            else {  
                return new IComponent[] {};  
            }  
        }  
    }  
    ```  
  
> [!NOTE]
>  il est également possible pour une classe dérivée de l'objet d' <xref:System.Drawing.Design.ToolboxItem> pour fournir sa propre implémentation autonome du contrôle sous\-jacent.  Cette classe est ensuite chargé de créer et de fournir tous les composants sous\-jacents.  
  
## ajout explicite des éléments de boîte à outils  
 Pour être ajouté à la boîte à outils, un contrôle doit être inclus dans une instance d' <xref:System.Drawing.Design.ToolboxItem> ou d'un objet dérivé d' <xref:System.Drawing.Design.ToolboxItem> puis être ajouté à **boîte à outils** à l'aide de l'interface d' <xref:System.Drawing.Design.IToolboxService> .  
  
#### pour encapsuler et ajouter des contrôles de boîte à outils  
  
1.  Incluez l'implémentation d' <xref:System.ComponentModel.Component> dans une instance d'un objet d' <xref:System.Drawing.Design.ToolboxItem> ou <xref:System.Drawing.Design.ToolboxItem>objet dérivé en appelant la méthode d' <xref:System.Drawing.Design.ToolboxItem.Initialize%2A> de cet objet avec <xref:System.Type?displayProperty=fullName>du composant implémentant :  
  
    ```vb#  
    Dim customItem As New ToolboxItem()   
    If customItem IsNot Nothing Then   
        customItem.Initialize(userControl)   
    End If  
    ```  
  
    ```c#  
    ToolboxItem customItem = new ToolboxItem() ;  
    if (customItem != null) {  
        customItem.Initialize(userControl);  
    }  
    ```  
  
     Est supérieure un exemple d'objet `userControl` dérivé d' <xref:System.Windows.Forms.UserControl> \(une instance de l'objet d' `ToolboxControl1` montré ci\-dessus\) utilisé pour construire nouvel <xref:System.Drawing.Design.ToolboxItem>.  
  
    > [!NOTE]
    >  L'implémentation par défaut du constructeur d' <xref:System.Drawing.Design.ToolboxItem> prend un argument d' <xref:System.Type?displayProperty=fullName> \(le constructeur d'<xref:System.Drawing.Design.ToolboxItem.%23ctor%28System.Type%29> appelle la méthode d' <xref:System.Drawing.Design.ToolboxItem.Initialize%2A> de l'objet d' <xref:System.Drawing.Design.ToolboxItem> .  
  
2.  Utilisez le service de boîte à outils \(<xref:System.Drawing.Design.IToolboxService>\) pour ajouter l'objet d' <xref:System.Drawing.Design.ToolboxItem> construit de l'implémentation du contrôle sous\-jacente.  
  
     Dans l'exemple ci\-dessous, l'accès au service de boîte à outils est obtenu, certaines des propriétés de l'instance `customItem` d' <xref:System.Drawing.Design.ToolboxItem> sont définies, puis `customItem` est ajouté à **boîte à outils**:  
  
    ```vb#  
    Dim toolboxService As IToolboxService = TryCast(GetService(GetType(IToolboxService)), IToolboxService)  
    customItem.Bitmap = New System.Drawing.Bitmap(ToolBoxControl1, "Control1.bmp")  
    customItem.DisplayName = "Custom Item"   
    toolboxService.AddToolboxItem(item, "Custom Tab")  
    ```  
  
    ```c#  
    IToolboxService toolboxService = GetService(typeof(IToolboxService)) as IToolboxService;  
    customItem.Bitmap = new System.Drawing.Bitmap(ToolboxControl1,"Control1.bmp");  
    customItem.DisplayName= "Custom Item";  
    toolboxService.AddToolboxItem(item, "Custom Tab");  
    ```  
  
## À l'aide de la réflexion pour ajouter des contrôles de boîte à outils  
 Appliquer des attributs à la classe implémentant un contrôle de boîte à outils permet l'environnement de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ou une application basée sur une [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)] d'utiliser la réflexion pour détecter automatiquement et ajouter correctement des contrôles à **boîte à outils**.  
  
#### pour appliquer la réflexion et les attributs aux contrôles de boîte à outils  
  
1.  Identifiez tous les objets utilisés pour implémenter les contrôles de boîte à outils à des instances d' <xref:System.ComponentModel.ToolboxItemAttribute>.  
  
     Le type d'instance d' <xref:System.ComponentModel.ToolboxItemAttribute> à une valeur d'objet détermine si et comment <xref:System.Drawing.Design.ToolboxItem> est construit à partir de celui\-ci.  
  
    1.  Appliquant une instance d' <xref:System.ComponentModel.ToolboxItemAttribute> est construit avec une valeur d' `BOOLEAN` d' `false` à un objet rend cet objet non disponible à la boîte à outils par réflexion.  
  
         Cela peut être utile pour isoler un objet, tel qu' <xref:System.Windows.Forms.UserControl> de **boîte à outils** pendant le développement.  
  
    2.  Appliquant une instance d' <xref:System.ComponentModel.ToolboxItemAttribute> est construit avec une valeur d' `BOOLEAN` d' `true` à un objet fait qu'objet disponible à la boîte à outils par réflexion et requiert que l'objet soit ajouté à la boîte à outils à l'aide d'un objet par défaut d' <xref:System.Drawing.Design.ToolboxItem> .  
  
    3.  Appliquant une instance d' <xref:System.ComponentModel.ToolboxItemAttribute> est construit avec <xref:System.Type> d'un objet personnalisé dérivé d' <xref:System.Drawing.Design.ToolboxItem> rend l'objet disponible à **boîte à outils** par réflexion et le requiert que l'objet soit ajouté à la boîte à outils en utilisant cet objet personnalisé dérivé d' <xref:System.Drawing.Design.ToolboxItem>.  
  
2.  Spécifiez \(au mécanisme de la réflexion de l'environnement de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] \) la bitmap à utiliser pour afficher le contrôle de boîte à outils dans **boîte à outils** en ajoutant une instance d' <xref:System.Drawing.ToolboxBitmapAttribute> à l'implémentation du contrôle de boîte à outils.  
  
3.  Si nécessaire, appliquez les instances d' <xref:System.ComponentModel.ToolboxItemFilterAttribute> aux objets d' <xref:System.Drawing.Design.ToolboxItem> à utilisent la réflexion pour les marquer statiquement à utiliser avec les objets qui ont un attribut correspondant.  
  
     Dans l'exemple ci\-dessous, l'implémentation d'un contrôle de boîte à outils contient une instance d' <xref:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute> appliquée à lui, ce qui rend ce contrôle disponible dans **boîte à outils** uniquement lorsque le document de travail actuel est de générateurs d' <xref:System.Windows.Forms.UserControl>  
  
    ```vb#  
    <ToolboxItemFilter(System.Windows.Forms.UserControl, ToolboxItemFilterType.Require)> _   
    <SerializableAttribute()> _   
    <GuidAttribute("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")> _   
    Friend Class CustomToolboxItem   
        Inherits ToolboxItem   
    End Class  
    ```  
  
    ```c#  
    [ToolboxItemFilter(System.Windows.Forms.UserControl,ToolboxItemFilterType.Require)]  
    [SerializableAttribute()]  //ToolboxItem implementations much has this attribute.  
    [GuidAttribute("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")]  
    internal class CustomToolboxItem : ToolboxItem   
    ```  
  
 Il existe trois techniques de base pour l'utilisation de la réflexion à charger automatiquement <xref:System.Drawing.Design.ToolboxItem>.  
  
### Utilisation des fonctionnalités de ToolService pour récupérer les contrôles de boîte à outils  
 <xref:System.Drawing.Design.ToolboxService> fournit à des VSPackages les méthodes statiques d' <xref:System.Drawing.Design.ToolboxService.GetToolboxItems%2A> qui utilisent la réflexion pour analyser des assemblys pour tous les types qui prennent en charge des éléments de boîte à outils, et retournent des éléments de ces types.  pour être retourné, un élément de boîte à outils doit :  
  
-   Être public.  
  
-   implémentez la classe d' <xref:System.ComponentModel.IComponent> .  
  
-   Ne pas être abstrait.  
  
-   Avez <xref:System.ComponentModel.ToolboxItemAttribute> sur son type.  
  
-   ne pas avoir <xref:System.ComponentModel.ToolboxItemAttribute> défini à `false` sur son type  
  
-   Ne pas contenir de paramètres génériques.  
  
##### pour obtenir cette liste  
  
1.  Créez une instance d' <xref:System.Reflection.Assembly> faisant référence à l'assembly qui doit être analysé pour les objets d' <xref:System.Drawing.Design.ToolboxItem> .  
  
    > [!NOTE]
    >  Pour obtenir une instance d' <xref:System.Reflection.Assembly> pour l'assembly actuel, utilisez la méthode statique <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>.  
  
2.  Appelez <xref:System.Drawing.Design.ToolboxService.GetToolboxItems%2A>, en retournant un objet d' <xref:System.Collections.ICollection> contenant une liste des objets appropriés.  
  
    > [!NOTE]
    >  Si un objet de <xref:System.Collections.ICollection> retourné a une instance valide d' <xref:System.Drawing.ToolboxBitmapAttribute> avez assigné à son implémentation, la méthode d' <xref:System.Drawing.Design.ToolboxService.GetToolboxItems%2A> définira la propriété d' <xref:System.Drawing.Design.ToolboxItem.Bitmap%2A> de l'objet d' <xref:System.Drawing.Design.ToolboxItem> .  
  
3.  Utilisez <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> pour obtenir l'accès à <xref:System.Drawing.Design.IToolboxService>, et utilisez sa méthode d' <xref:System.Drawing.Design.IToolboxService.AddToolboxItem%2A> pour ajouter des éléments de l'objet retourné d' <xref:System.Collections.ICollection> à la boîte à outils.  
  
     Le code suivant interroge l'application active et obtient une liste de tous ses objets d' <xref:System.Drawing.Design.ToolboxItem> et les charge.  Pour obtenir un exemple en illustrant cela en exécution du code, consultez la méthode d' `Initialization` dans [Procédure pas à pas : personnalisation dynamique de la configuration des éléments de la boîte à outils](../misc/walkthrough-customizing-toolbox-item-configuration-dynamically.md).  
  
    ```vb#  
    Protected ToolboxItemList As ICollection = Nothing  
    ToolboxItemList = ToolboxService.GetToolboxItems(Assembly.GetExecutingAssembly(), "")  
    If ToolboxItemList Is Nothing Then   
        Throw New ApplicationException("Unable to generate a toolbox Items listing for " & [GetType]().FullName)   
    End If   
    Dim toolboxService As IToolboxService = TryCast(GetService(GetType(IToolboxService)), IToolboxService)   
    For Each itemFromList As ToolboxItem In ToolboxItemList   
        toolboxService.AddToolboxItem(itemFromList, CategoryTab)   
    Next  
    ```  
  
    ```c#  
    protected ICollection ToolboxItemList = null;  
    ToolboxItemList = ToolboxService.GetToolboxItems(Assembly.GetExecutingAssembly(), "");  
    if (ToolboxItemList == null){  
        throw new ApplicationException("Unable to generate a toolbox Items listing for "  
    + GetType().FullName);  
    }  
    IToolboxService toolboxService = GetService(typeof(IToolboxService)) as IToolboxService;  
    foreach (ToolboxItem itemFromList in ToolboxItemList){  
        toolboxService.AddToolboxItem(itemFromList, CategoryTab);  
    }  
    ```  
  
### Utiliser les ressources incorporées de texte pour charger automatiquement les contrôles de boîte à outils  
 Une ressource de texte dans un assembly contenant une liste correctement mise en forme de contrôles de boîte à outils peut être utilisée par <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> pour charger automatiquement un contrôle de boîte à outils si correctement mise en forme.  
  
 Une ressource de texte contenant une liste d'objets au chargement doit être disponible dans un assembly accessible au VSPackage.  
  
##### Pour ajouter et rendre disponible une ressource de texte à l'assembly  
  
1.  Dans **Explorateur de solutions**, cliquez avec le bouton droit sur le projet.  
  
2.  Le point à **Ajouter**, cliquez sur **Nouvel élément**.  
  
3.  dans la boîte de dialogue d' **Ajouter un nouvel élément** , sélectionnez **Fichier texte** et fournissez un nom.  
  
4.  Dans **Explorateur de solutions**, cliquez avec le bouton droit sur le fichier texte venant d'être créé et définissez la propriété d' **Action de génération** à la ressource incorporée.  
  
     Les entrées pour que le contrôle de **boîte à outils** soit chargé doivent contenir le nom de la classe d'implémentation, le nom de l'assembly contenant la.  
  
     Pour plus d'informations sur le format des entrées de contrôles de boîte à outils à la ressource incorporée en texte, consultez la page de référence d' <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> .  
  
5.  Installez un chemin de recherche des fichiers contenant les assemblys qui héberge les objets de contrôle de boîte à outils.  
  
     <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A>, dossiers de recherche uniquement spécifiés dans l'entrée du Registre HKEY\_CURRENT\_USER \\Software\\Microsoft\\VisualStudio \\ *\<version\>* \\AssemblyFolders, où  *\<version\>*  est le numéro de version de la version Visual Studio \(par exemple, 8,0\).  
  
    > [!NOTE]
    >  Le chemin d'accès racine HKEY\_LOCAL\_MACHINE \\SOFTWARE\\Microsoft\\VisualStudio \\ *\<Version\>*  peut être substitué par une autre racine lorsque le shell Visual Studio est initialisé, ou l'utilisation d' <xref:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute>.  Pour plus d'informations, consultez [Commutateurs de ligne de commande](../Topic/Command-Line%20Switches%20\(Visual%20Studio%20SDK\).md).  
  
     Pour plus d'informations sur le format correct des entrées du Registre d'AssemblyFolder, consultez la page de référence d' <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> .  
  
6.  Obtenez une instance d' <xref:System.IO.TextReader.Synchronized%2A> accès à la ressource incorporée de texte, et, si la prise en charge de la localisation est nécessaire pour les noms de catégories, une instance d' <xref:System.Resources.ResourceManager>, puis utilise ces derniers pour appeler la méthode d' <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> .  
  
    ```vb#  
    Dim rm As New ResourceManager("TbxCategories", Assembly.GetExecutingAssembly())  
    Dim toolboxStream As Stream = TbxItemProvider.[GetType]().Assembly.GetManifestResourceStream("ToolboxItems.txt")  
    If toolboxStream IsNot Nothing Then   
        Using reader As TextReader = New StreamReader(toolboxStream)   
            ParseToolboxResource(reader, rm)   
        End Using   
    End If  
    ```  
  
    ```c#  
    ResourceManager rm = new ResourceManager("TbxCategories", Assembly.GetExecutingAssembly());  
    Stream toolboxStream = TbxItemProvider.GetType().Assembly.GetManifestResourceStream("ToolboxItems.txt");  
    if (toolboxStream != null) {  
        using (TextReader reader = new StreamReader(toolboxStream)) {  
        ParseToolboxResource(reader, rm);  
    }  
    }  
    ```  
  
     Dans l'exemple ci\-dessus, une liste contenue dans une ressource incorporée en texte dans l'assembly contenant la classe `TbxItemProvider` est passée à <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> avec les ressources de type chaîne en `TbxCategories` .  
  
     La méthode recherche tous les fichiers qui contiennent les assemblys dans les répertoires spécifiés sous l'entrée du Registre d'AssemblyFolders pour les contrôles de boîte à outils répertoriés dans la ressource et les chargera.  
  
    > [!NOTE]
    >  Si un contrôle de boîte à outils trouvé par <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> a une instance valide d' <xref:System.Drawing.ToolboxBitmapAttribute> avez assigné à son implémentation, <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> définira la bitmap utilisée pour afficher le contrôle de boîte à outils.  
  
### Explicitement à l'aide de la réflexion pour charger automatiquement les contrôles de boîte à outils  
 S'il est nécessaire d'interroger explicitement des assemblys pour plus d'informations sur les contrôles de **boîte à outils** qu'ils contiennent, plutôt que déléguant la tâche à <xref:System.Drawing.Design.ToolboxService.GetToolboxItems%2A>, vous pouvez le faire.  
  
##### Pour utiliser explicitement la réflexion pour charger automatiquement les contrôles de boîte à outils  
  
1.  Créez une instance d' <xref:System.Reflection.Assembly>, en faisant référence à chaque assembly qui doit être analysé pour les objets d' <xref:System.Drawing.Design.ToolboxItem> .  
  
    > [!NOTE]
    >  Pour obtenir une instance d' <xref:System.Reflection.Assembly> pour l'assembly actuel, utilisez la méthode statique <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>.  
  
2.  Pour chaque assembly soit analysé, utilisez la méthode d' <xref:System.Reflection.Assembly.GetTypes%2A> de l'objet d' <xref:System.Reflection.Assembly> pour obtenir une liste de chaque <xref:System.Type?displayProperty=fullName> dans l'assembly.  
  
3.  Vérifiez que le type n'est pas abstraite et ne prend pas en charge l'interface d' <xref:System.ComponentModel.IComponent> \(toutes les implémentations des contrôles de boîte à outils utilisés pour instancier un objet d' <xref:System.Drawing.Design.ToolboxItem> doivent implémenter cette interface\).  
  
4.  Obtenir les attributs d' <xref:System.Type> et utilisez ces informations pour déterminer si le VSPackage souhaite charger l'objet.  
  
    > [!NOTE]
    >  Bien que dans l'entité de sécurité qu'il est possible de créer un objet d' <xref:System.Drawing.Design.ToolboxItem> d'une implémentation d'interface d' <xref:System.ComponentModel.IComponent> sans instance d' <xref:System.ComponentModel.ToolboxItemAttribute> non définie à `false` est appliqué à lui, nous déconseillons de le faire.  
  
5.  Utilisez <xref:System.Type.GetConstructor%2A> pour obtenir des constructeurs pour les objets d' <xref:System.Drawing.Design.ToolboxItem> que les contrôles de boîte à outils requièrent.  
  
6.  Construisez des objets d' <xref:System.Drawing.Design.ToolboxItem> et ajoutez \-les à **boîte à outils**.  
  
 Pour voir un exemple illustrer l'utilisation explicite de la réflexion pour obtenir et charger automatiquement les contrôles de boîte à outils, consultez `CreateItemList` décrit dans [Procédure pas à pas : chargement automatique d’éléments de boîte à outils](../misc/walkthrough-autoloading-toolbox-items.md).  
  
## Configuration du contrôle de boîte à outils supplémentaires  
 Un VSPackage peut avoir de mieux contrôler le moment où et comment un contrôle de boîte à outils est affiché par **boîte à outils**, via l'implémentation d' <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem>, et l'utilisation d' <xref:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute>, et l' <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute>.  
  
 Appliquer des instances d' <xref:System.ComponentModel.ToolboxItemFilterAttribute> à une classe fournit uniquement le contrôle statique moment où et comment un contrôle de **boîte à outils** est disponible.  
  
#### Pour créer la prise en charge dynamique de configuration des contrôles de boîte à outils  
  
1.  Créez une classe qui implémente l'interface d' <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> dans le cadre d'un VSPackage.  
  
    > [!NOTE]
    >  l'interface d' <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> ne doit pas être implémentée sur la même classe qui fournit l'implémentation d'un VSPackage d' <xref:Microsoft.VisualStudio.Shell.Package>.  
  
2.  Associez l'implémentation d' <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> avec les objets des assemblys spécifiques en appliquant une instance d' <xref:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute> lui.  
  
     L'exemple suivant fournit la possibilité de configuration dynamique pour les assemblys d'objet contrôle de boîte à outils dans l'espace de noms et requièrent d' `Vsip.*` que certains objets d' <xref:System.Drawing.Design.ToolboxItem> soient visibles uniquement avec les concepteurs basés sur d' <xref:System.Windows.Forms.UserControl>et autre jamais visible avec les concepteurs basés sur d' <xref:System.Windows.Forms.UserControl>.  
  
    ```vb#  
    <ProvideAssemblyFilterAttribute("Vsip.*, Version=*, Culture=*, PublicKeyToken=*")> _   
    <GuidAttribute("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")> _   
    Public NotInheritable Class ToolboxConfig   
        Implements IConfigureToolboxItem   
        Public Sub New()   
        End Sub  
  
        ''' <summary>   
        ''' Adds extra configuration information to this toolbox item.   
        ''' </summary>   
        Public Sub ConfigureToolboxItem(ByVal item As ToolboxItem)   
            If item Is Nothing Then   
                Exit Sub   
            End If   
  
            'hide from .NET Compact Framework on the device designer.   
            Dim newFilter As ToolboxItemFilterAttribute = Nothing   
            If item.TypeName = GetType(ToolboxControl1).ToString() Then   
                newFilter = New ToolboxItemFilterAttribute("System.Windows.Forms.UserControl", ToolboxItemFilterType.Require)   
            ElseIf item.TypeName = GetType(ToolboxControl2).ToString() Then   
  
                newFilter = New ToolboxItemFilterAttribute("System.Windows.Forms.UserControl", ToolboxItemFilterType.Prevent)   
            End If   
            If newFilter IsNot Nothing Then   
                Dim array As New ArrayList()   
                array.Add(newFilter)   
                item.Filter = DirectCast(array.ToArray(GetType(ToolboxItemFilterAttribute)), ToolboxItemFilterAttribute())   
            End If   
        End Sub   
    End Class  
    ```  
  
    ```c#  
    [ProvideAssemblyFilterAttribute("Vsip.*, Version=*, Culture=*, PublicKeyToken=*")]  
        [GuidAttribute("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")]  
        public sealed class ToolboxConfig : IConfigureToolboxItem {  
            public ToolboxConfig() {  
            }  
  
            /// <summary>  
            ///     Adds extra configuration information to this toolbox item.  
            /// </summary>  
            public void ConfigureToolboxItem(ToolboxItem item) {  
                if (item == null)  
                    return;  
  
                //hide from .NET Compact Framework  on the device designer.  
                ToolboxItemFilterAttribute newFilter = null;  
                if (item.TypeName == typeof(ToolboxControl1).ToString()) {  
                    newFilter = new ToolboxItemFilterAttribute("System.Windows.Forms.UserControl",  
                                                          ToolboxItemFilterType.Require);  
                }   
                else if (item.TypeName == typeof(ToolboxControl2).ToString()) {  
  
                    newFilter = new ToolboxItemFilterAttribute("System.Windows.Forms.UserControl",  
                                                          ToolboxItemFilterType.Prevent);  
                }  
                if (newFilter != null) {  
                    ArrayList array = new ArrayList();  
                    array.Add(newFilter);  
                    item.Filter = (ToolboxItemFilterAttribute[])  
                            array.ToArray(typeof(ToolboxItemFilterAttribute));  
                }  
            }  
        }  
    }  
    ```  
  
3.  Enregistrez un VSPackage comme fourniture d'une implémentation spécifique d' <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> en appliquant une instance d' <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute> à l'implémentation du VSPackage d' <xref:Microsoft.VisualStudio.Shell.Package>.  
  
     L'exemple ci\-dessous informerait à l'environnement de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] que le package implémenté par `Vsip.ItemConfiguration.ItemConfiguration` fournit la classe `Vsip.ItemConfiguration.ToolboxConfiguration` à la dynamique <xref:System.Drawing.Design.ToolboxItem>de stockage.  
  
    ```vb#  
    <ProvideToolboxItemsAttribute(3)> _   
    <DefaultRegistryRoot("Software\Microsoft\VisualStudio\8.0")> _   
    <InstalledProductRegistration(False, "#100", "#102", "1.0", IconResourceID := 400)> _   
    <ProvideLoadKey("Standard", "1.0", "Package Name", "Company", 1)> _   
    <ProvideMenuResource(1000, 1)> _   
    <ProvideToolboxItemConfigurationAttribute(GetType(ToolboxConfig))> _   
    <GuidAttribute("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")> _   
    Public Class ItemConfiguration   
        Inherits Package   
    End Class  
    ```  
  
    ```c#  
    [ProvideToolboxItemsAttribute(3)]  
    [DefaultRegistryRoot("Software\\Microsoft\\VisualStudio\\8.0")]  
    [InstalledProductRegistration(false, "#100", "#102", "1.0", IconResourceID = 400)]  
    [ProvideLoadKey("Standard", "1.0", "Package Name", "Company", 1)]  
    [ProvideMenuResource(1000, 1)]  
    [ProvideToolboxItemConfigurationAttribute(typeof(ToolboxConfig))]  
  
    [GuidAttribute("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")]  
    public class ItemConfiguration : Package  
    ```  
  
## Prise en charge du glisser\-déplacer personnalisée  
 En plus de être ajouté à **boîte à outils** lui\-même, des objets d' <xref:System.Drawing.Design.ToolboxItem> et leurs implémentations peuvent être utilisés pour étendre la prise en charge du glisser\-déplacer dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] l'IDE.  Cela peut permettre les formats de presse\-papiers arbitraires à exposer à **boîte à outils** et dans les éditeurs.  
  
 VSPackages en fonction de managed package doit stocker en tant que spécification des formats de presse\-papiers personnalisés d'élément de **boîte à outils** , en appliquant une instance d' <xref:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute> à la classe implémentant <xref:Microsoft.VisualStudio.Shell.Package>.  
  
 Pour plus d'informations sur l'enregistrement comme fournisseur de **boîte à outils** , consultez [Inscription des fonctionnalités de prise en charge de boîte à outils](../misc/registering-toolbox-support-features.md).  
  
#### Pour fournir aux formats de presse\-papiers personnalisés et à la prise en charge du glisser\-déplacer les contrôles de boîte à outils  
  
1.  créez une implémentation du délégué d' <xref:System.Drawing.Design.ToolboxItemCreatorCallback> .  
  
     Cette implémentation doit retourner un objet d' <xref:System.Drawing.Design.ToolboxItem> qui prend en charge le format de presse\-papiers non standard.  
  
     Pour obtenir un exemple d'implémentation d'un délégué d' <xref:System.Drawing.Design.ToolboxItemCreatorCallback> , consultez les pages de référence de <xref:System.Drawing.Design.ToolboxItem> et d' <xref:System.Drawing.Design.ToolboxItemCreatorCallback> .  
  
2.  Faites cette implémentation du délégué d' <xref:System.Drawing.Design.ToolboxItemCreatorCallback> disponible à [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] **boîte à outils** pour une boîte à outils non standard en appelant <xref:System.Drawing.Design.IToolboxService.AddCreator%2A>.  
  
    ```vb#  
    <GuidAttribute("7D91995B-A799-485e-BFC7-C52545DFB5DD")> _   
    <ProvideToolboxFormatAttribute("MyFormat")> _   
    Public Class ItemConfiguration   
        Inherits MSVSIP.Package   
        Public Overloads Overrides Sub Initialize()   
            '"Adding this class as a ToolboxItemCreator");   
            Dim toolbox As IToolboxService = DirectCast(host.GetService(GetType(IToolboxService)), IToolboxService)   
            If toolbox IsNot Nothing Then   
                toolboxCreator = New ToolboxItemCreatorCallback(Me.OnCreateToolboxItem)   
                toolbox.AddCreator(toolboxCreator, "MyFormat", host)   
            End If   
        End Sub   
    End Class  
    ```  
  
    ```c#  
    [GuidAttribute("7D91995B-A799-485e-BFC7-C52545DFB5DD")]  
    [ProvideToolboxFormatAttribute("MyFormat")]  
    public class ItemConfiguration : MSVSIP.Package  
    {  
        public override void Initialize() {   
            /*  
            *  
            */  
            //"Adding this class as a ToolboxItemCreator");  
            IToolboxService toolbox = (IToolboxService)host.GetService(typeof(IToolboxService));  
            if (toolbox != null) {  
                toolboxCreator = new ToolboxItemCreatorCallback(this.OnCreateToolboxItem);  
                toolbox.AddCreator(toolboxCreator, "MyFormat", host);  
            }  
            private ToolboxItem OnCreateToolboxItem(object serializedData, string format) {  
               /*  
                *  
                */  
            }  
        }  
    }  
    ```  
  
### Dans cette section  
 [Comment : prendre en charge la fonctionnalité glisser\-déplacer de la boîte à outils](../misc/how-to-support-toolbox-drag-and-drop-functionality.md)  
 Décrit comment implémenter la prise en charge du glisser\-déplacer dans une vue du document.  
  
 [Comment : fournir des éléments de boîte à outils personnalisés à l’aide d’assemblys d’interopérabilité](../misc/how-to-provide-custom-toolbox-items-by-using-interop-assemblies.md)  
 Décrit l'ajout de nouveaux contrôles ActiveX et nouveaux éléments à [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] **boîte à outils**.  ces nouveaux éléments peuvent avoir un format de presse\-papiers standard ou un format personnalisé pris en charge par le VSPackage.  
  
 [Inscription des fonctionnalités de prise en charge de boîte à outils](../misc/registering-toolbox-support-features.md)  
 Décrit comment inscrire un VSPackage comme fournisseur de boîte à outils.  parle également de prendre en charge ou d'utiliser d'autres fonctionnalités de boîte à outils.  
  
## Voir aussi  
 [Extension de la boîte à outils](../misc/extending-the-toolbox.md)   
 [Procédures pas à pas de la Boîte à outils](../misc/toolbox-walkthroughs.md)   
 [Inscription des fonctionnalités de prise en charge de boîte à outils](../misc/registering-toolbox-support-features.md)   
 [Comment : fournir des éléments de boîte à outils personnalisés à l’aide d’assemblys d’interopérabilité](../misc/how-to-provide-custom-toolbox-items-by-using-interop-assemblies.md)   
 [Gestion de la boîte à outils](../misc/managing-the-toolbox.md)   
 [Comment : contrôler la boîte à outils](../Topic/How%20to:%20Control%20the%20Toolbox.md)