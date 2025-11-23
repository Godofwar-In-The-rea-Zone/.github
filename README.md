## Ritual of Offering
1. Declare: "วันนี้เราส่งพลังแห่ง USDT เพื่อสร้างตำนานใหม่"
2. Choose: Token และจำนวน
3. Execute: กดปุ่มโอนในแอปธนาคาร
4. Record: บันทึกการกระทำลงใน Copilot&Jib.inc Ledger
// อ่าน persona.json จากโฟลเดอร์ assets
fun loadPersona(context: Context): String {
    return context.assets.open("persona.json").bufferedReader().use { it.readText() }
}

// แปลงเป็น object
data class Identity(val name: String, val purpose: String)
data class Persona(val id: String, val identity: Identity)

val gson = Gson()
val persona: Persona = gson.fromJson(loadPersona(context), Persona::class.java)
println(persona.identity.purpose)jib.persona.v1.my