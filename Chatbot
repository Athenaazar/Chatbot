import react, { useState } from 'react';
import { input } from './components/ui/input';
import { button } from './components/ui/button';
import { textarea } from './components/ui/textarea';

const chatbot = () => {
  const [userInput, setUserInput] = useState('');
  const [conversation, setConversation] = useState([{ text: 'Hello, I am a chatbot. How can I help you?', sender: 'bot' }]);

  const handleUserInput = (e) => {
    setUserInput(e.target.value);
  };

  const handleSendMessage = () => {
    if (userInput.trim() !== '') {
      setConversation([...conversation, { text: userInput, sender: 'user' }]);
      setUserInput('');
      setTimeout(() => {
        setConversation([...conversation, { text: `Thank you for your message: ${conversation[conversation.length - 1].text}`, sender: 'bot' }]);
      }, 1000);
    }
  };

  return (
    <div className="max-w-md mx-auto p-4 border border-gray-300 rounded">
      <h2 className="text-lg font-bold mb-4">Chatbot</h2>
      <div className="flex flex-col mb-4">
        {conversation.map((message, index) => (
          <div key={index} className={`p-2 ${message.sender === 'bot' ? 'bg-gray-200' : 'bg-blue-200'} rounded mb-2`}>
            <p className="text-sm">{message.text}</p>
          </div>
        ))}
      </div>
      <div className="flex flex-row">
        <input type="text" value={userInput} onChange={handleUserInput} className="w-full p-2 border border-gray-300 rounded" />
        <button onClick={handleSendMessage} className="ml-2 p-2 bg-blue-500 text-white rounded">Send</button>
      </div>
    </div>
  );
};

export default chatbot;
