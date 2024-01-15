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


import SwiftUI

struct WelcomeView: View{
    
    @AppStorage("UserName") var UserName:String = ""
    
    var body: some View{
        VStack{
            Text(UserName.isEmpty ? "" : UserName)
                .font(.system(size: 50))
            Image("whd")
                .resizable()
                .frame(width: 400, height: 550)
                .position(x:200, y:180)
            Text("歡迎光臨棣球村")
                .font(.system(size:28, design: .rounded))
                .position(x:200, y:225)
                .lineSpacing(5)
                .foregroundStyle(.purple)
                .multilineTextAlignment(.center)
        }
        .padding(.top, 20)
        /* VStack{
         Image("mobiledevtw")
         .resizable()
         .aspectRatio(contentMode: .fit)
         Text("資訊技術培訓\nWeb/APP/AI應用開發")
         .fontWeight(.heavy)
         .lineSpacing(20)
         .font(.system(size: 32.0))
         .foregroundColor(.white)
         .frame(width: 350, height: 150, alignment: .center)
         .background(Color.blue)
         .cornerRadius(20.0)
         .multilineTextAlignment(.center)
         }*/
    }
}


import SwiftUI

struct Drama: Identifiable {
    var id = UUID()
    var name: String
    var image: String
    var description: String
}

var drama = [
    Drama(name: "許七安", image: "sqa", description: "大奉打更人"),
    Drama(name: "時宴", image: "sy", description: "以愛為營"),
    Drama(name: "程嘉樹", image: "cjs", description: "戰火中的青春"),
    Drama(name: "郭文翰", image: "gwh", description: "抬頭見喜"),
    Drama(name: "白馬帥", image: "bms", description: "今日宜加油"),
    Drama(name: "肖鐸", image: "xd", description: "浮圖緣"),
    Drama(name: "東方青蒼", image: "dfcc", description: "蒼蘭訣"),
    Drama(name: "尉遲龍炎", image: "ycly", description: "遇龍"),
    Drama(name: "祁曉", image: "qx", description: "理智派生活"),
    Drama(name: "寧缺", image: "nq", description: "將夜2"),
    Drama(name: "道明寺", image: "dms", description: "流星花園"),
]

struct BasicImageRow: View {
    var thisDrama: Drama
    var body: some View{
        HStack{
            Image(thisDrama.image)
                .resizable()
                .frame(width: 40, height: 40)
                .cornerRadius(5)
            Text(thisDrama.name)
        }
    }
}

struct DramaDetailView: View{
    @Environment(\.presentationMode) var presentationMode
    var thisDrama: Drama
    var body: some View{
        ScrollView{
            VStack{
                Image(thisDrama.image)
                    .resizable()
                    .aspectRatio(contentMode: /*@START_MENU_TOKEN@*/.fill/*@END_MENU_TOKEN@*/)
                    .clipped()
                Text(thisDrama.name)
                    .font(.system(.title, design: .rounded))
                    .fontWeight(.black)
                Spacer()
                Text(thisDrama.description)
                    .font(.system(.subheadline, design: .rounded))
                    .fontWeight(.light)
                Spacer()
            }
        }
        .overlay(
            HStack{
                Spacer()
                VStack{
                    Button(action:{
                        self.presentationMode.wrappedValue.dismiss()
                    }, label:{
                        Image(systemName: "chevron.down.circle.fill")
                            .font(.largeTitle)
                            .foregroundColor(.white)
                    })
                    .padding(.trailing, 20)
                    .padding(.top, 40)
                    Spacer()
                }
            }
        )
    }
}

struct DramaListView: View {
    @State var showDetailView = false
    @State var selectedDrama: Drama?
    var body: some View {
        NavigationView {
            List(drama){ dramaItem in BasicImageRow(thisDrama: dramaItem)
                    .onTapGesture {
                        self.showDetailView = true
                        self.selectedDrama = dramaItem
                    }
            }
            .sheet(item: self.$selectedDrama){
                thisDrama in DramaDetailView(thisDrama: thisDrama)
            }
            .navigationBarTitle("戲劇列表")
        }
    }
}


import SwiftUI

struct TermAndDescription: Identifiable{
    var id = UUID()
    var term: String
    var description: String
}

var myDictionary = [
    TermAndDescription(term: "大奉打更人", description: "騰訊"),
    TermAndDescription(term: "以愛為營", description: "芒果"),
    TermAndDescription(term: "戰火中的青春", description: "優酷"),
    TermAndDescription(term: "抬頭見喜", description: "愛奇藝"),
    TermAndDescription(term: "今日宜加油", description: "愛奇藝"),
    TermAndDescription(term: "浮圖緣", description: "愛奇藝"),
    TermAndDescription(term: "蒼蘭訣", description: "愛奇藝"),
    TermAndDescription(term: "遇龍", description: "騰訊"),
    TermAndDescription(term: "理智派生活", description: "芒果"),
    TermAndDescription(term: "將夜2", description: "騰訊"),
    TermAndDescription(term: "流星花園", description: "芒果"),
]

struct CardView: View {
    @State var currentCard = 0
    var body: some View {
        VStack{
            VStack{
                Text(myDictionary[currentCard].term)
                    .font(.title)
                    .foregroundColor(.yellow)
                    .padding(.all, 10)
                Text(myDictionary[currentCard].description)
                    .font(.body)
                    .foregroundColor(.white)
                    .padding(.all, 10)
            }
            .frame(minWidth: 0, idealWidth: 100, maxWidth: 300, minHeight: 0, idealHeight: 300, maxHeight: 300, alignment: .center)
            .background(Color.purple)
            .onTapGesture{
                if currentCard<myDictionary.count-1{
                    currentCard+=1
                }else{
                    currentCard=0
                }
            }
            Text("點擊查看下一張")
                .padding(.all, 10)
        }
    }
}


```
