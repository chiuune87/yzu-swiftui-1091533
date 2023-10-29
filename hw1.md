<h1>HW1</h1>
      
 ```swift
import SwiftUI

struct ContentView: View {
    var body: some View {
        Image("cherry")
            .resizable()
            .aspectRatio(contentMode: /*@START_MENU_TOKEN@*/.fill/*@END_MENU_TOKEN@*/)
            .overlay(
                Text("  Play N Be Real")
                    .fontWeight(.heavy)
                    .lineSpacing(10)
                    .font(.system(size:32.0))
                    .foregroundColor(.white)
                    .frame(width: 260, height: 80, alignment: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/)
                    .background(Color.gray)
                    .cornerRadius(30.0)
                    .opacity(0.8)
                ,
                alignment: .bottom
            )
            .overlay(
                Text("    謝馥謙\n 1091533")
                    .fontWeight(.bold)
                    .font(.title)
                    .padding()
                    .position(x:250, y:550)
                    .foregroundColor(.white)
            )
            .overlay(
                Image(systemName: "signature.th")
                    .font(.system(size:100))
                    .foregroundColor(.purple)
                    .shadow(color: .yellow, radius: 5, x: 5, y: 5)
                ,
                alignment: .top
            )
    }
}


 ```

<img width="40%" src="https://raw.githubusercontent.com/chiuune87/yzu-swiftui-1091533/main/hw1.jpg">
