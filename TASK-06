#include <iostream>
#include <string>
#include <map>

using namespace std;

class Room {
public:
    string description;
    map<string, Room*> exits;

    Room(string desc) : description(desc) {}

    void addExit(string direction, Room* room) {
        exits[direction] = room;
    }

    void describe() {
        cout << description << endl;
        cout << "Exits: ";
        for (const auto& exit : exits) {
            cout << exit.first << " ";
        }
        cout << endl;
    }
};

class Player {
public:
    int score;
    Room* currentRoom;

    Player(Room* startRoom) : score(0), currentRoom(startRoom) {}

    void move(string direction) {
        if (currentRoom->exits.find(direction) != currentRoom->exits.end()) {
            currentRoom = currentRoom->exits[direction];
            cout << "You move to a new room." << endl;
        } else {
            cout << "You can't go that way!" << endl;
        }
    }

    void takeItem(string item) {
        cout << "You took the " << item << "." << endl;
        score += 10;
    }

    void showScore() {
        cout << "Your score: " << score << endl;
    }
};

int main() {
    Room* startRoom = new Room("You are in a small room with stone walls. It smells like damp earth.");
    Room* secondRoom = new Room("You are in a dimly lit room. There is a shiny sword on the ground.");
    Room* thirdRoom = new Room("You are in a library filled with ancient books. There is a strange glowing book on a table.");

    startRoom->addExit("north", secondRoom);
    secondRoom->addExit("south", startRoom);
    secondRoom->addExit("east", thirdRoom);
    thirdRoom->addExit("west", secondRoom);

    Player player(startRoom);

    string action;
    while (true) {
        player.currentRoom->describe();
        cout << "What do you want to do? (Move, Take, Score, Quit): ";
        getline(cin, action);

        if (action == "Move") {
            string direction;
            cout << "Which direction? (north, south, east, west): ";
            getline(cin, direction);
            player.move(direction);
        } else if (action == "Take") {
            string item;
            cout << "Which item do you want to take? (sword, book): ";
            getline(cin, item);
            player.takeItem(item);
        } else if (action == "Score") {
            player.showScore();
        } else if (action == "Quit") {
            cout << "Thanks for playing!" << endl;
            break;
        } else {
            cout << "Invalid action. Try again." << endl;
        }
    }

    delete startRoom;
    delete secondRoom;
    delete thirdRoom;

    return 0;
}
