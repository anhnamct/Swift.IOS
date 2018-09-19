# Swift.IOS

//enum ten chu cai dau viet hoa, cac case ben trog viet thuong
enum Level {
    case low,medium,high
}
enum Size:Int {
    case nho = 1, trungbinh = 2, to = 3
}
var myLevel = Level.high
var myLevel2: Level = .low
var mySize = Size.trungbinh.rawValue
print(myLevel)
print(myLevel2)
print(mySize)

// chung ta co the su dung switch doi voi enum
switch myLevel {
case .low:
    print("Level cua ban qua thap")
case .medium:
    print("Level cua ban muc trung binh")
case .high:
    print("Level cua ban qua rat cao")
default:
    print("Ban khong co level")
}
// ta co the khoi tao enum voi cac gia tri ben trong co the thay the duoc
enum ApppleDevice {
    case apppleWatch(String, String)
    case appleIphone(Float,String)
}
var myDevice:ApppleDevice = .appleIphone(10.3, "trang")
// trong switch, o moi case ta can them "let" de chuong trinh hieu la ta dang switch thang AppleDevice
switch myDevice {
case let .appleIphone(version, color):
    print("Iphone version: \(version), color: \(color)")
case let .apppleWatch(name, color):
    print("Apple Watch name: \(name), color: \(color)")
default:
    print("Not Apple Watch or Iphone")
}

// Associated value(gia tri lien ket) cho phep chung ta luu tru them du lieu o ben trong enum
enum AccountSro {
    case character1(level: Level, banghoi: String)
    case character2(level: Level, banghoi: String)
    case character3(level :Level, banghoi: String)
}
var myAccount1:AccountSro = .character1(level: .low, banghoi: "Cai Bang")
var myAccount2:AccountSro = .character2(level: .medium, banghoi: "Thieu Lam")
var myAccount3:AccountSro = .character3(level: .high, banghoi: "Den Do")

switch myAccount1 {
case let .character1(level,banghoi):
    print("Character 1 cua ban co level: \(level), bang hoi: \(banghoi)")
case let .character2(level,banghoi):
    print("Character 2 cua ban co level: \(level), bang hoi: \(banghoi)")
case let .character3(level,banghoi):
    print("Character 3 cua ban co level: \(level), bang hoi: \(banghoi)")
default:
    print("Ban k co character nao trong game")
}
