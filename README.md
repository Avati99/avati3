import { useState } from 'react';
import { ThumbsUp, ThumbsDown, RefreshCcw } from 'lucide-react';

const VoteComponent = () => {
  const [upvotes, setUpvotes] = useState(0);
  const [downvotes, setDownvotes] = useState(0);

  const resetVotes = () => {
    setUpvotes(0);
    setDownvotes(0);
  };

  return (
    <div className="flex flex-col items-center p-4 bg-gray-100 rounded-2xl shadow-lg w-64">
      <div className="flex justify-between w-full mb-4">
        <button
          className="flex items-center gap-2 px-4 py-2 bg-green-500 text-white rounded-lg hover:bg-green-600"
          onClick={() => setUpvotes(upvotes + 1)}
        >
          <ThumbsUp size={20} /> {upvotes}
        </button>
        <button
          className="flex items-center gap-2 px-4 py-2 bg-red-500 text-white rounded-lg hover:bg-red-600"
          onClick={() => setDownvotes(downvotes + 1)}
        >
          <ThumbsDown size={20} /> {downvotes}
        </button>
      </div>
      <button
        className="flex items-center gap-2 px-4 py-2 bg-gray-500 text-white rounded-lg hover:bg-gray-600"
        onClick={resetVotes}
      >
        <RefreshCcw size={20} /> Сброс
      </button>
    </div>
  );
};

export default VoteComponent;
