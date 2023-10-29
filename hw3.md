<h1>HW3</h1>
      
 ```swift
import SwiftUI
struct ContentView: View{
    var body: some View{
        VStack{
            TitleView()
            HStack{
                ProductView(imageName: "PeaceBird")
                    .frame(height:500)
                
                VStack{
                    ProductView(imageName: "Maybelline")
                    ProductView(imageName: "Sabon")
                    ProductView(imageName: "Bolon")
                }
                .frame(height:500)
                
                VStack{
                    ProductView(imageName: "Colgate")
                    ProductView(imageName: "EsteeLauder")
                    ProductView(imageName: "Guerlain")
                }
                .frame(height:500)
            }
            
            ZStack{
                ProductView(imageName: "Juice")
                Text("保存期限:2023/12/20")
                    .font(.system(size:15))
                    .foregroundColor(.yellow)
                    .padding(.all, 5)
                    .background(Color.black)
                    .opacity(0.7)
                    .offset(x:100, y:40)
            }
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

struct PView: View{
    var body: some View{
        VStack{
            Image("PeaceBird")
                .resizable()
                .aspectRatio(contentMode: .fit)
                .frame(width: UIScreen.screenWidth/2-20, alignment:.center)
            Text("PeaceBird")
                .fontWeight(.bold)
                .font(.system(size:30))
        }
    }
} 

struct MView: View{
    var body: some View{
        VStack{
            Image("Maybelline")
                .resizable()
                .aspectRatio(contentMode: .fit)
                .frame(width: UIScreen.screenWidth/2-20, alignment:.center)
            Text("Maybelline")
                .fontWeight(.bold)
                .font(.system(size:30))
        }.padding(.all, 2)
    }
}

struct SView: View{
    var body: some View{
        VStack{
            Image("Sabon")
                .resizable()
                .aspectRatio(contentMode: .fit)
                .frame(width: UIScreen.screenWidth/2-20, alignment:.center)
            Text("Sabon")
                .fontWeight(.bold)
                .font(.system(size:30))
        }.padding(.all, 2)
    }
}

struct BView: View{
    var body: some View{
        VStack{
            Image("Bolon")
                .resizable()
                .aspectRatio(contentMode: .fit)
                .frame(width: UIScreen.screenWidth/2-20, alignment:.center)
        }.padding(.all, 2)
        Text("Bolon")
            .fontWeight(.bold)
            .font(.system(size:30))
    }
}

struct CView: View{
    var body: some View{
        VStack{
            Image("Colgate")
                .resizable()
                .aspectRatio(contentMode: .fit)
                .frame(width: UIScreen.screenWidth/2-20, alignment:.center)
            Text("Colgate")
                .fontWeight(.bold)
                .font(.system(size:30))
        }.padding(.all, 2)
    }
}

struct EView: View{
    var body: some View{
        VStack{
            Image("EsteeLauder")
                .resizable()
                .aspectRatio(contentMode: .fit)
                .frame(width: UIScreen.screenWidth/2-20, alignment:.center)
            Text("EsteeLauder")
                .fontWeight(.bold)
                .font(.system(size:30))
        }.padding(.all, 2)
    }
}

struct GView: View{
    var body: some View{
        VStack{
            Image("Guerlain")
                .resizable()
                .aspectRatio(contentMode: .fit)
                .padding(.all, 15)
            Text("Guerlain")
                .fontWeight(.bold)
                .font(.system(size:30))
        }
    }
}

extension UIScreen{
    static let screenWidth = UIScreen.main.bounds.size.width
    static let screenHeight = UIScreen.main.bounds.size.height
    static let screenSize = UIScreen.main.bounds.size
}

struct ProductView: View{
    var imageName: String
    var body: some View{
        VStack{
            Image(imageName)
                .resizable()
                .aspectRatio(contentMode: .fit)
                .frame(width: UIScreen.screenWidth/2-20, alignment:.center)
            Text(imageName)
                .font(.system(size:25))
        }
        .frame(minWidth: /*@START_MENU_TOKEN@*/0/*@END_MENU_TOKEN@*/, idealWidth: /*@START_MENU_TOKEN@*/100/*@END_MENU_TOKEN@*/, maxWidth: /*@START_MENU_TOKEN@*/.infinity/*@END_MENU_TOKEN@*/, minHeight: /*@START_MENU_TOKEN@*/0/*@END_MENU_TOKEN@*/, idealHeight: 100, maxHeight: /*@START_MENU_TOKEN@*/.infinity/*@END_MENU_TOKEN@*/, alignment: /*@START_MENU_TOKEN@*/.center/*@END_MENU_TOKEN@*/)
    }
}

struct TitleView: View {
    var body: some View {
        HStack (alignment:.center, spacing:2){
            Text("鶴羽的")
                .font(.system(size:30))
                .fontWeight(.bold)
            Text("收藏櫃")
                .font(.title)
                .fontWeight(.bold)
                .foregroundColor(Color(red: 180/255, green: 0/255, blue: 192/255))
        }
    }
}



 ```

<img width="40%" src="https://raw.githubusercontent.com/chiuune87/yzu-swiftui-1091533/main/hw3.PNG">
