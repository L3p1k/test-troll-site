app = Flask(__name__)

mem_list = [
    'ты лох',
    'ты бот',
    'ку-ку лошара!)',
    'я твой рот вычислю сейчас)))',
    'АНЕКДОТ! заходит значит пацан к барыге, ну и барыга ему такой: сышишь гранату за 5рублей хошь? пацан не думая такой: да ну ты гонишь конечно давай. Барыга даёт ему и говорит: на держи, ток за кольцо гони ещё две сотни!'
    ]

@app.route('/')
def home():
    return "<a href='/mem_list'>Посмотреть случайный рофл</a>"

@app.route('/mem_list')
def mem():
    random_mem = random.choice(mem_list)
    return f"<p>{random_mem}</p><br><a href='/'>Назад</a>"

app.run(debug=True)