<h1>HW4</h1>
      
 ```swift
import SwiftUI

struct ContentView: View {
    var body: some View {
        VStack {
            Text("")
            Text("王鶴棣的角色牆")
                .font(.largeTitle)
                .fontWeight(.heavy)
                .foregroundStyle(.primary)
            TabView{
                Group{
                    WelcomeView()
                        .tabItem { 
                            Image(systemName: "rosette")
                            Text("Welcome")
                        }
                    DramaListView()
                        .tabItem { 
                            Image(systemName: "list.dash")
                            Text("Courses")
                        }
                    CardView()
                        .tabItem { 
                            Image(systemName: "book")
                            Text("Learn")
                        }
                }
                .toolbarBackground(Color.black, for: .tabBar)
                .toolbarBackground(.visible, for: .tabBar)
                /*.toolbarColorScheme(.dark, for: .tabBar)*/
            }
            .tint(.yellow)
        }
    }
}
```
