heroes = {
    1: "Layla", 2: "Tigreal", 3: "Gusion", 4: "Kagura", 5: "Chou"
}

ign = input("IGN: ")
rank = input("Rank: ")

matches = []
wins = 0

# Loop for 4 matches based on your example
for i in range(1, 5):
    print(f"\nMatch {i}")
    try:
        choice = int(input("Hero Number (1-5, or 0 to skip): "))
    except ValueError:
        print("Skipped (Invalid Input)")
        continue
    
    # FIX 1: Allow skipping with 0
    if choice == 0:
        print(f"Match {i} : skipped")
        continue
    elif choice not in heroes:
        print("Invalid Hero! Skipped.")
        continue

    k = int(input("Kills: "))
    d = int(input("Deaths: "))
    a = int(input("Assists: "))
    res = input("Win or Loss? (W/L): ").upper()

    # FIX 2: Handle KDA and avoid division by zero
    score = (k + a) / d if d > 0 else float(k + a)
    
    # Performance Feedback Logic
    status = "DOMINATION!" if score >= 5 else "Better Luck Next Game"

    matches.append({
        "id": i,
        "hero": heroes[choice], 
        "score": score, 
        "res": res,
        "status": status
    })

    if res == "W":
        wins += 1

# Summary Output
print(f"\n--- {ign} ({rank}) ---")

best_match = None

for m in matches:
    print(f"Match {m['id']} : {m['hero']} | KDA: {m['score']:.2f} | {m['res']} → {m['status']}")
    
    # Track Best Match
    if best_match is None or m['score'] > best_match['score']:
        best_match = m

# Final Analytics
if matches:
    print(f"\nBest match: [{best_match['id']}] {best_match['hero']} with KDA {best_match['score']:.2f}.")
    win_rate = (wins / len(matches)) * 100
    print(f"Win rate: {wins}/{len(matches)} × 100 = {win_rate:.0f}%")
else:
    print("\nNo matches were recorded.")
