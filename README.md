# PageMenu

 var controllernames = ["Home","youtube","Swift",]
    var carbonTabSwipeNavigation = CarbonTabSwipeNavigation()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
        
        carbonTabSwipeNavigation = CarbonTabSwipeNavigation(items: controllernames, delegate: self)
        
        carbonTabSwipeNavigation.setIndicatorColor(UIColor.green)
        carbonTabSwipeNavigation.setIndicatorHeight(10)
        
        carbonTabSwipeNavigation.setTabBarHeight(50)
        
      //  carbonTabSwipeNavigation.setNormalColor(UIColor.lightGray, font: UIFont(name: "Font Awesome 5 Free", size: 30)!)
       // carbonTabSwipeNavigation.setSelectedColor(UIColor.blue, font: UIFont(name: "Font Awesome 5 Free", size: 30)!)
        
        carbonTabSwipeNavigation.carbonSegmentedControl?.backgroundColor = UIColor.black
        carbonTabSwipeNavigation.carbonSegmentedControl?.setWidth(view.frame.width / 3, forSegmentAt: 0)
        carbonTabSwipeNavigation.carbonSegmentedControl?.setWidth(view.frame.width / 3, forSegmentAt: 1)
        carbonTabSwipeNavigation.carbonSegmentedControl?.setWidth(view.frame.width / 3, forSegmentAt: 2)
       // carbonTabSwipeNavigation.carbonSegmentedControl?.setWidth(view.frame.width / 3, forSegmentAt: 4)

        
        carbonTabSwipeNavigation.setCurrentTabIndex(1, withAnimation: true)
        
        carbonTabSwipeNavigation.carbonSegmentedControl?.indicatorPosition = .top
        
        carbonTabSwipeNavigation.insert(intoRootViewController: self)
    }
    
    func carbonTabSwipeNavigation(_ carbonTabSwipeNavigation: CarbonTabSwipeNavigation, viewControllerAt index: UInt) -> UIViewController {
        guard let storyboard = storyboard else { return UIViewController() }
        if index == 0
        {
            return storyboard.instantiateViewController(identifier: "ViewController1")
        }
        else if index == 1
        {
            return storyboard.instantiateViewController(identifier: "TableViewController")
        }
        else
        {
            return storyboard.instantiateViewController(identifier: "CollectionViewController")
        }
    }
    
    func carbonTabSwipeNavigation(_ carbonTabSwipeNavigation: CarbonTabSwipeNavigation, willMoveAt index: UInt) {
        print(index)
    }

