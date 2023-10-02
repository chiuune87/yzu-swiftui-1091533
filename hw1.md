<h1>HW1</h1>
      
 ```swift
    import SwiftUI
    struct ContentView: View {
        var body: some View {
            Image("dylan-wang")
                .resizable()
                .aspectRatio(contentMode: /*@START_MENU_TOKEN@*/.fill/*@END_MENU_TOKEN@*/)
                .overlay(
                    Text("  Play N \n Be Real")
                        .fontWeight(.heavy)
                        .lineSpacing(20)
                        .font(.system(size:32.0))
                        .foregroundColor(.white)
                        .frame(width: 250, height: 150, alignment: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/)
                        .background(Color.purple)
                        .cornerRadius(30.0)
                        .opacity(/*@START_MENU_TOKEN@*/0.8/*@END_MENU_TOKEN@*/)
                    ,
                    alignment: .bottom
                )
        }
    }

 ```

<img width="40%" src="https://raw.githubusercontent.com/chiuune87/yzu-swiftui-1091533/main/IMG_2278.jpeg">
