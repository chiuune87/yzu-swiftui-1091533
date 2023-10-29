<h1>HW2</h1>
      
 ```swift
import SwiftUI

class Game{
    var randomInt: Int
    var symbol: String
    init(){
        randomInt = Int.random(in:0...2)
        
        if randomInt == 0 {
            symbol = "剪刀"
        } else if randomInt == 1 {
            symbol = "石頭"
        } else {
            symbol = "布"
        }
    }
}


struct ContentView: View {
    @State var game = Game()
    var body: some View{
        VStack{
            Text(String(game.symbol))
                .padding(.all,10)
                .frame(width: 300, height: 120, alignment: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/)
                .font(.system(size: 100))
            Button(action: {
               game = Game()
            }, label: {
                Text("Go")
                    .padding(.all,10)
                    .frame(width: 300, height: 100, alignment: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/)
                    .font(.system(size: 50))
                    .background(Color.purple)
                    .foregroundColor(.white)
                    .border(Color.purple, width: 5)
                    .cornerRadius(20)
            })
        }
    }
}


 ```

[![hw2](https://res.cloudinary.com/marcomontalbano/image/upload/v1698568341/video_to_markdown/images/youtube--7u11M1IPeVY-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/7u11M1IPeVY?si=wZjCVwvCSo7oD9qg "hw2")
